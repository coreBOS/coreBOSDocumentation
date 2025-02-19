---
title: 'Vtiger + popup + llamada entrante + cola'
metadata:
    description: 'Vtiger + popup + llamada entrante + cola'
    author: 'Joe Bordes'
content:
    items:
        - '@self.children'
    limit: 5
    order:
        by: date
        dir: desc
    pagination: true
    url_taxonomy_filters: true
taxonomy:
    category:
        - development
        - asterisk
    tag:
        - integration
---

Artículo publicado [en este blog](http://robert-sp-86.blogspot.com/2012/03/vtiger-popup-llamada-entrante-cola.html) y replciado aquí para que no se pierda.

===

Se supone configurado el módulo PBX Manager del Vtiger CRM correctamente.

Vtiger CRM, permite que un usuario registrado en él, reciba notificaciones de llamadas entrantes a su extensión. Esta extensión, necesariamente deberá ser especificada en el módulo de Configuración del CRM. Para llegar hasta allí, una vez autenticado, haga click en el link " Configuración " y luego click en el link "Usuarios". Seguidamente aparecerán todos los usuarios registrados en el Vtiger. Al hacer click en el nombre de algún usuario, aparecerá un formulario con su información disponible para ser modificada si usted cuenta con los privilegios.

Existe un campo de texto que es para colocar el número de extensión de Elastix. Esta extensión deberá estar previamente registrada en dicho servidor de comunicaciones unificadas. Si usted es usuario del CRM, puede hacer click en link "Mis preferencias" (zona superior derecha de la página) y llenar su propio perfil. Para poder recibir notificaciones de llamadas, deberá introducir un número de extensión, ya registrado en el servidor Elastix, que usted previamante habrá asociado con el CRM, en el campo correspondiente.

Si usted está autenticado en el Vtiger, y su extensión recibe una llamada, se mostrará un "popup" como notificación de que la está recibiendo. Pero existe una limitante. Si su extensión recibe una llamada procedente de una cola… no le llegará a usted la notificación.

El fichero cron/modules/PBXManager/AsteriskClient.php tiene como función escuchar los eventos que se llevan acabo en el servidor que contiene a Asterisk. En este fichero, existe la función "asterisk_handleResponse1". Esta función filtra los eventos que hacen "Ring" a través de esta condición:

```php
if (
   (($mainresponse['Event'] == 'Newstate' || $mainresponse['Event'] == 'Newchannel') && ($mainresponse[$state] == 'Ring') 
   || ($mainresponse['Event'] == 'Newstate' && $mainresponse[$state] == 'Ringing'))
)
```

Y la función "asterisk_handleResponse2" filtra los eventos de la siguiente forma:

```php
if (
   $mainresponse['Event'] == 'Newexten' && (strstr($appdata, "__DIALED_NUMBER")
   || strstr($appdata, "EXTTOCALL"))
)
```

Los eventos que no se capturen en asterisk_handleResponse1, pasarán a ser filtrados por asterisk_handleResponse2 y los que no, por asterisk_handleResponse3, el resto de los eventos no son tomados en cuenta.

El flujo de una llamada entrante hasta que se muestra el popup es el siguiente: (se supone corriendo el fichero AsteriskClient.php)

1-) Llamada entrante dispara los eventos Newstate y/o Newchannel que contienen los headers: ChannelStateDesc (en la version 1.6) o State (en la version 1.4) cuyos valores pueden ser "Ring" o "Ringing". Y son capturados en asterisk_handleResponse1. Ejemplos de eventos:

```
Event: Newstate
Privilege: call,all
Channel: SIP/11179-0000f060
ChannelState: 4
ChannelStateDesc: Ring
CallerIDNum: 11179
CallerIDName: device
Uniqueid: 1330550725.97318

Event: Newstate
Privilege: call,all
Channel: Local/95155@from-queue-392a;1
ChannelState: 5
ChannelStateDesc: Ringing
CallerIDNum: 11179
CallerIDName: CallCenter79
Uniqueid: 1330550733.97321
```

2) asterisk_handleResponse1 inserta evento en la tabla vtiger_asteriskincomingevents con atributo flag = -1

3) Se espera otro evento que pase por filtro de la función asterisk_handleResponse2. Si hay algún evento que cumpla con la condición, se actualiza la tabla vtiger_asteriskincomingevents modificando el atributo flag = 0 donde el atributo Uniqueid se igual al de algún evento anteriormente insertado por la función asterisk_handleResponse1. Se verifica que este evento modificado tenga el atributo from_number (número del llamante) con algún número de teléfono. Si es así y se cumple que el atributo to_number posee un número de extensión registrado en el servidor donde corre Asterisk:

4) Se procede a insertar en la tabla vtiger_asteriskincomingcalls desde donde se leerán las llamadas entrantes para poder lanzar el popup.

5) La función asterisk_IncomingEventCleanup se encarga de borrar los registros viejos de vtiger_asteriskincomingevents.

Hasta aqui llega el flujo de la llamada desde el punto de vista del fichero AsteriskClient.php.

## Solución:
La única condición para que esto funcione es que la cola desde donde se reciben las llamadas, sus miembros no sean agentes, si no extensiones. Sucede que he revisado los eventos generados por asterisk cuando se reciben llamadas en las extensiones que están conectados los agentes, ningún evento contiene el número de extensión que recibe el ring del llamante. Pero sin embargo cuando la cola, como miembros, no tiene agentes, sino extensiones, pues se generan eventos que contienen el número de extensión destino, o sea el miembro de la cola que recibe la llamada. De esta forma el popup sí puede mostrarse en la página del usuario que tiene asociada esta extensión, incluso las llamadas directas a su extensión. Esta solución no impide que se reciban notificaciones por llamadas directas.

El código, no me dediqué a optimizarlo, en cuanto hallé la solución, pues enseguida la estoy publicando.

Por qué no funciona el popup cuando la llamada proviene de una cola?

1) En la función handleResponse1 cuando una llamada hace Ring, o está haciendo Ringing se filtra por el evento "Newstate" o "Newchannel". Eso está bien, pero sucede, que las cabeceras CallerIDName (from_name) y CallerIDNum (from_number) están vacías cuando provienen de una cola. Y eso es un inconveniente porque se guarda el evento en la tabla asteriskincomingevents con estos datos en null y cuando se le consulta no hay forma de saber quien llama y entonces la notificación no se puede llevar cabo.

2) En la función handleResponse2 cuando una llamada viene de una cola, el evento que se dispara es "Dial". Esta función no tenía filtro para este evento en la la primera condicional "if" de la función. Y es precisamente este evento el que contiene la información del llamante y el receptor de la llamada. Una vez conocido esto, es cuando se pueden actualizar los datos del evento en la tablaasteriskincomingevents teniendo en cuenta que ya se había insertado el evento, con estos datos vacíos, desde la función handleResponse1 . Una vez encontrado el Uniqueid o UniqueID del registrado en la función anterior, se actualizan los atributos from_name, from_number y to_number de la tabla asteriskincomingevents. Y con estos datos actualizados ya es posible isertar en la tabla asteriskincomingcalls, desde la cual, el script TraceIncomingCall.php puede saber las llamadas entrantes para poder construir el popup con los datos.

Las funciones asterisk_handleResponse1 y asterisk_handleResponse2 están descritas debajo, con las modificaciones que permiten que funcione el popup.

```php
diff --git a/cron/modules/PBXManager/AsteriskClient.php b/cron/modules/PBXManager/AsteriskClient.php
index 1478c86e2..81f5df121 100644
--- a/cron/modules/PBXManager/AsteriskClient.php
+++ b/cron/modules/PBXManager/AsteriskClient.php
@@ -112,10 +112,18 @@ function asterisk_handleResponse1($mainresponse, $state, $adb) {
                if (!empty($mainresponse['CallerIDName'])) {
                        $callerName = $mainresponse['CallerIDName'];
                }
-               $channel = $mainresponse['Channel'];
-
-               $sql = 'INSERT INTO vtiger_asteriskincomingevents (uid, channel, from_number, from_name, timer, flag) VALUES(?,?,?,?,?,?)';
-               $adb->pquery($sql, array($uniqueid, $channel, $callerNumber, $callerName, time(), -1));
+               $resultado = $adb->pquery('SELECT COUNT(uid) as cant FROM vtiger_asteriskincomingevents WHERE flag=-1 and uid=?', array($uniqueid));
+               if ($adb->query_result($resultado, 0, 'cant')>0 && !empty($callerNumber)) {
+                       $adb->pquery(
+                               'UPDATE vtiger_asteriskincomingevents SET from_number=?, timer=?, from_name=? WHERE uid=?',
+                               array($callerNumber, time(), $callerName, $uniqueid)
+                       );
+               } else {
+                       $adb->pquery(
+                               'INSERT INTO vtiger_asteriskincomingevents (uid, channel, from_number, from_name, timer, flag) VALUES(?,?,?,?,?,?)',
+                               array($uniqueid, $mainresponse['Channel'], $callerNumber, $callerName, time(), -1)
+                       );
+               }
                return false;
        }
        return true;
@@ -124,6 +132,7 @@ function asterisk_handleResponse1($mainresponse, $state, $adb) {
 function asterisk_handleResponse2($mainresponse, $adb, $asterisk, $state) {
        $appdata = isset($mainresponse['AppData']) ? $mainresponse['AppData'] : '';
        $uniqueid = $channel = $callerType = $extension = null;
+       $dial_event = false;
        $parseSuccess = false;
        if ($mainresponse['Event'] == 'Newexten' && (strstr($appdata, '__DIALED_NUMBER') || strstr($appdata, 'EXTTOCALL'))) {
                $uniqueid = $mainresponse['Uniqueid'];
@@ -133,6 +142,16 @@ function asterisk_handleResponse2($mainresponse, $adb, $asterisk, $state) {
                $splits = explode('=', $appdata);
                $extension = $splits[1];
                $parseSuccess = true;
+       } elseif ($mainresponse['Event'] == 'Dial' && !empty($mainresponse['SubEvent']) && $mainresponse['SubEvent'] == 'Begin') {
+               $uniqueid = $mainresponse['Uniqueid'];
+               $channel = $mainresponse['Channel'];
+               $splits = explode('/', $channel);
+               $callerType = $splits[0];
+               $extension = $mainresponse['Dialstring'];
+               $caller = $mainresponse['CallerIDNum'];
+               $name = $mainresponse['CallerIDName'];
+               $dial_event = true;
+               $parseSuccess = true;
        } elseif ($mainresponse['Event'] == 'OriginateResponse') {
                //if the event is OriginateResponse then its an outgoing call and set the flag to 1, so that AsteriskClient does not pick up as incoming call
                $uniqueid = $mainresponse['Uniqueid'];
@@ -143,6 +162,12 @@ function asterisk_handleResponse2($mainresponse, $adb, $asterisk, $state) {
                if (checkExtension($extension, $adb)) {
                        $sql = 'UPDATE vtiger_asteriskincomingevents SET to_number=?, callertype=?, timer=?, flag=? WHERE uid=?';
                        $adb->pquery($sql, array($extension, $callerType, time(), 0, $uniqueid));
+                       if ($dial_event) {
+                               $adb->pquery(
+                                       'UPDATE vtiger_asteriskincomingevents SET from_number=?, to_number=?, from_name=?, callertype=?, timer=?, flag=? WHERE uid=?',
+                                       array($caller, $extension, $name,$callerType, time(), 0, $uniqueid)
+                               );
+                       }
                        $callerinfo = $adb->pquery('SELECT from_number,from_name FROM vtiger_asteriskincomingevents WHERE uid = ?', array($uniqueid));
                        if ($adb->num_rows($callerinfo) > 0) {
                                $callerNumber = $adb->query_result($callerinfo, 0, 'from_number');
popupllamadaentrantecola.diff
```

[popupllamadaentrantecola.diff](https://discussions.corebos.org/documentation/lib/exe/fetch.php?media=en:devel:corebospbx:popupllamadaentrantecola.diff)