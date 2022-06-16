---
title: 'Physical Support'
metadata:
    description: 'This asset-like module records all the external devices and support hardware being used by an account. Necessary for inventory knowledge and legal requirements.'
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
        - extension
    tag:
        - module
---
---
This asset-like module records all the external devices and support hardware being used by an account. Necessary for inventory knowledge and legal requirements.

===

### Fields

#### LBL\_SOPORTES\_INFORMATION

<table class="table table-striped">
<thead>
<tr class="header">
<th>Field</th>
<th>Type</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr>
<td>registro_no</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>soporte_no</td>
<td>autonumber</td>
<td></td>
</tr>
<tr>
<td>Tipo</td>
<td>picklist</td>
<td>Pen Drive USB,CD,DVD,ZIP,HD USB,Cinta DAT,Disquete 3,5,
PDA,Armario / Archivador Bajo Llave,Soporte Papel,SAN,HD EXTERNO</td>
</tr>
<tr>
<td>Contenido</td>
<td>picklist</td>
<td>Copia de Seguridad,Listados,Doc. Trabajo,Correo Electrónico,
Expedientes Académicos,Expediente Laboral,Doc. Proveedores,
Doc. Fiscal / Contable,Doc. Calidad,Informes Psicopedagógicos,
Información alumnos</td>
</tr>
<tr>
<td>Ubicacion</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Fecha de Alta</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Soporte Movil</td>
<td>checkbox</td>
<td></td>
</tr>
<tr>
<td>Texto Soporte Movil</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>RespSeg</td>
<td>relation</td>
<td>Contacts,Empleados</td>
</tr>
<tr>
<td>Medidas de seguridad adicionales adoptadas</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Created Time</td>
<td>datetime</td>
<td></td>
</tr>
<tr>
<td>Modified Time</td>
<td>datetime</td>
<td></td>
</tr>
<tr>
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
<tr>
<td>Description</td>
<td>text</td>
<td></td>
</tr>
<tr>
<td>tovalidate</td>
<td>checkbox</td>
<td></td>
</tr>
<tr>
<td>Destruido</td>
<td>checkbox</td>
<td></td>
</tr>
<tr>
<td>Cuenta</td>
<td>relation</td>
<td>Accounts</td>
</tr>
<tr>
<td>Plantilla</td>
<td>relation</td>
<td>Documents</td>
</tr>
<tr>
<td>NumSerie</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Borrar contenido</td>
<td>checkbox</td>
<td></td>
</tr>
</tbody>
</table>
<br>
#### Custom Information
<br>
#### Discontinued Information

<table class="table table-striped">
<thead>
<tr class="header">
<th>Field</th>
<th>Type</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr>
<td>MetodoDestruccion</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>DestInfo</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Fecha de baja</td>
<td>date</td>
<td></td>
</tr>
</tbody>
</table>
<br>
#### Clave de cifrado

<table class="table table-striped">
<thead>
<tr class="header">
<th>Field</th>
<th>Type</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr>
<td>Clave de cifrado</td>
<td>text</td>
<td></td>
</tr>
</tbody>
</table>
