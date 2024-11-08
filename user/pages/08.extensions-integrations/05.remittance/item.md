---
title: 'Bank Remittance (Remesa)'
metadata:
    description: 'Send Remittance/Remesas to the bank following Norm 19 and 58'
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
        - course
    tag:
        - Remittance
        - Remesa
        - Bank
        - norm19
        - norm58
        - norma19
        - norma58
        - sepa
---

## Send Remittance to the bank following Norm 19 and 58
## Remesa Bancaria SEPA, Normas 19 y 58

Módulo que nos permite agrupar facturas según cualquier filtro que se pueda crear en la aplicación y generar el fichero bancario con las normas SEPA, 19 o 58 preparado para subir al banco para el cobro.

En el módulo de remesas podremos crear un registro para cada exportación que deseamos realizar. Este módulo es idéntico a cualquier otro módulo y su funcionamiento es el mismo. Al crear un registro de remesa, nos encontraremos con una serie de campos que nos ayudarán a controlar las remesas pendientes, las cuentas bancarias de la empresa y otros detalles.

Asociado a cada registro de la remesa encontramos una serie de listas relacionadas. Una de ellas es el conjunto de facturas asociadas a la remesa. Para definir el conjunto de facturas que queremos enviar en la remesa utilizamos los botones disponibles en la lista relacionada. Así podemos crear una nueva factura que quedará asociada a la remesa, podemos seleccionar de una en una y también podemos eliminar cualquier factura de la lista mediante la acción de borrar disponible en cada factura de la lista.

Además, cualquier filtro que podamos crear en el módulo de facturas estará disponible en la lista relacionada para poder cargar masivamente un conjunto de facturas. De esta manera podríamos crear un filtro de "Facturas pendientes de pago" y cargarlas mensualmente en la remesa con suma facilidad.

Una vez seleccionada el conjunto de facturas de la remesa, creamos la remesa mediante la acción en el panel derecho. Esto generará el fichero y lo añadirá al sistema como un documento (disponible en el módulo de documentos) y lo relacionará con la remesa, así en la lista relacionada encontraremos el fichero a enviar al banco.

Si se produce cualquier error en la generación, el nombre del fichero será ERROR y contendrá una descripción del problema.

La extensión nos guarda un histórico de las exportaciones, tanto de la misma remesa como de todas las generadas en el pasado. Nos permite seleccionar o eliminar de manera individual cualquier factura y tiene un procesamiento posterior manual para ayudar a marcar las facturas devueltas y cobradas.

### SEPA

Instalando el zip desde la configuración (como cualquier otro módulo), instalará 4 módulo diferentes:

- Bancos
- Cuentas bancarias
- Órdenes de domiciliación (Mandatos)
- Remesas

Bancos y cuentas bancarias sirven para administrar TUS PROPIAS cuentas, es decir dónde se ingresaran las remesas.

En estos módulos tienes que introducir al menos un banco y una cuenta bancaria relacionada con ese banco.

En la cuenta bancaria tendrás que introducir el obligatoriamente el sufijo (3 dígitos), esa información está relacionada con tu contrato con el banco y tendrás que pedírsela a ellos (usualmente es 000, aunque puede ser otro numero)

Después tendrás que introducir las órdenes de domiciliación de tus clientes, si ya tienes información de la cuenta bancaria en coreBOS, tenemos una herramienta de migración a Ordenes de domiciliacion, aunque depende mucho de como esté introducida la información de la cuenta, si necesitas migrar las cuentas, contáctanos y revisamos como lo haríamos.

Los parámeros básicos de las ordenes de domiciliación son:

- Cuenta (Cliente) relacionada
- IBAN
- BIC
- Tipo de Pago (si es un pago único o se va a utilizar más veces)
- Tipo de débito (básico o B2B, normalmente será B2B, eso también depende del contrato con tu banco)
- Fecha Firma (la fecha en la que se firma la orden)
- Lugar firma (el lugar)
- Pagos permitidos (si el pago es recurrente tienes un numero determinado de pagos permitidos, en este campo es donde se indica, esto depende de la relación con tu cliente)

Una vez creada la orden puedes descargarte un PDF para que lo firme tu cliente.

Las órdenes de domiciliación se tienen que relacionar con las facturas para poder pasarlas a la remesa (te aparecerá un campo en la factura), en cualquier caso, si cuando exportas la remesa fallara alguna cosa, el sistema te lo indica en el campo Resultado de la exportación en el registro de la remesa.

Ahora ya pasamos a crear la remesa y añadir facturas, al crear la remesa te pedirá una referencia (cualquier cosa que te sirva para identificarla), la cuenta bancaria y la fecha. Una vez creada ya puedes añadir facturas en el apartado de facturas de la remesa (es una lista relacionada en la parte inferior)

Aqui puedes elegir qué facturas incluyes en la remesa, desde una ventana emergente o bien cargar una lista completa utilizando los filtros que tengas en facturas. De esta manera si tienes organizadas las facturas de una manera determinada, puedes, con un sólo botón, incluir las que te interesen.

Una vez relacionadas las facturas, con el botón Generar exportación (en la parte derecha) generaras un archivo xml que puedes enviar al banco usando el sistema que tenga para ello. Este archivo lo encontrarás en el apartado Remesa dentro del mismo registro.

En el campo "Resultado de la exportación" tendrás un resumen del resultado, si ha habido algún error (puede faltar información) te lo indica, y si todo ha ido bien, verás que tipos de debito has enviado, el total de cada uno y qué facturas se incluyen.

Para que no salgan todas las órdenes de Domiciliación al elegir una desde la Factura o Albarán y que sólo salgan las relacionadas con la cuenta del mismo, hay que aplicar el parchelinkmnd.diff, que está en la carpeta modules/Mandate

Vídeo con una demostración aquí:

[plugin:youtube](https://youtu.be/zissi-7ES8E)

Como con casi todas nuestras extensiones la hemos adaptado para diversos clientes, haciendo, por ejemplo, las remesas contra nuestro módulo de Cobros y Pagos, permitiendo, así hacer remesas de cobros parciales en vez de facturas enteras.

Ponte en [contacto con nosotros para más información](https://corebos.com/contact).

<div class="notices blue">
<h3>¿Donde añades la cuenta bancaria del deudor de la factura?</h3>
</div>

Al instalar la extensión se añaden campos para la cuenta bancaria en la cuenta y en la factura. Al crear la factura se copia el valor de la cuenta bancaria de la cuenta en los campos correspondientes de la factura. Al realizar la remesa se utilizan los valores de la factura.

De esta manera se utiliza la cuenta bancaria por defecto de la cuenta pero se puede modificar ciertas facturas para cargarlas en otra cuenta bancaria.

<div class="notices blue">
<h3>No veo los campos de la cuenta de banco en factura por ningún sitio en la demo. ¿me puedes indicar donde están?</h3>
</div>

No está instalado en la demo. Esa parte se instala cuando instalamos la norma 19, ahora mismo en la demo solo hay un exportación genérica que no requiere la funcionalidad de la cuenta bancaria.

<div class="notices blue">
<h3>¿Si tienes que modificar la cantidad a remesar porque solo le cobres parte de la factura (la mitad, por ejemplo), se puede hacer?</h3>
</div>

No, en este caso has de hacer una factura por la mitad y pasarla por el banco, después ya harás la otra factura. Lo que por temas de impuestos también es lo más recomendable.

<div class="notices blue">
<h3>En la lista desplegable aparece "acc1", ¿dónde se modifica/crea el valor de este campo?</h3>
</div>

Las cuentas de vuestra empresa, deben aparecer en la lista desplegable. Esto se hace en el editor de listas desplegables en configuración. Solo lo puede hacer un usuario administrador.

<div class="notices blue">
<h3>¿Puedes explicar cómo funciona la lista relacionada?</h3>
</div>

El funcionamiento de la lista relacionada es exactamente como el funcionamiento de la lista en campañas, podéis leer sobre ello en el manual. el tema es que cargáis en la lista SOLO las facturas a remesar, o sea, no cargáis toda la lista de las facturas, sino solo aquellas que queréis que aparezcan en la remesa. Eso lo podéis conseguir de tres maneras:

- creando un filtro en facturas, por ejemplo, un filtro de "facturas no pagadas de la semana pasada", y cargáis ese filtro en la remesa
- seleccionando manualmente las facturas a remesar, para esto tenéis el botón de seleccionar
- añadiendo, o sea, creando nuevas facturas

Un vez las tenéis en la lista podéis eliminar alguna que se haya cargado sin querer mediante el botón de eliminar, esto solo elimina la factura de la remesa, no elimina la factura en sí.

En cuanto tengáis cargadas las facturas a remesar, basta pulsar sobre la acción de generar remesa para obtener el fichero a mandar al banco.

<div class="notices blue">
<h3>¿No debería de crearse automáticamente un campo llamado algo así como "Fecha de Pago" en cada factura?</h3>
</div>

coreBOS ya lleva un campo llamado exactamente así (Due Date). No recuerdo si el proceso de validación de la remesa recibida actualiza este campo pero eso se podría añadir si hiciera falta. En cualquier caso el campo ya existe y solo tenéis que actualizarlo. Como tenéis el campo de remesa en las facturas es bastante sencillo filtrar por el mismo y actualizar la fecha utilizando la edición masiva.

<div class="notices blue">
<h3>He añadido un número de cuenta en a una de las cuentas que tenemos. A continuación, creé una factura nueva para esa cuenta, pero el número de cuenta que habíamos escrito no aparece por ningún lado automáticamente de la factura en el campo "Cuenta bancaria", ¿es así el funcionamiento?</h3>
</div>

Para que se rellene automáticamente el número de cuenta hay que crear la factura desde la lista relacionada de la cuenta. O sea, elige la cuenta desde el módulo de cuentas, accede a la pestaña de "Mas Información", abre la lista factura y pulsa sobre el botón de "Añadir Factura", así te quedará todo rellenado, la empresa, la cuenta bancaria y la dirección.

También puedes crear un mapa de dependencia de campos para capturar la información que necesites.