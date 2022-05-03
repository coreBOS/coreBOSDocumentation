---
title: 'Access Registration'
metadata:
    description: 'This module records all access different people do upon certain assets. Necessary for inventory knowledge and legal requirements.'
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

This module records all access different people do upon certain assets. Necessary for inventory knowledge and legal requirements.

===

### Fields


#### LBL_REGACCESO_INFORMATION

<table class="table table-striped">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr>
<td>Title</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
<tr>
<td>Account Name</td>
<td>relation</td>
<td>Accounts</td>
</tr>
<tr>
<td>Responsable</td>
<td>relation</td>
<td>Empleados,Contacts</td>
</tr>
<tr>
<td>Fichero</td>
<td>relation</td>
<td>Fichero</td>
</tr>
<tr>
<td>Fecha acceso</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Hora acceso</td>
<td>time</td>
<td></td>
</tr>
<tr>
<td>TipoAcceso</td>
<td>picklist</td>
<td>FisicoTerceros,FisicoNoAuto,FisicoAuto,Otros,ACCESS_OK,
ACCESS_NOK_BADDEV,ACCESS_NOK_DESTROY,
ACCESS_NOK_DEVRETIRED,ACCESS_NOK_BADUSER,
ACCESS_NOK_BADPASS</td>
</tr>
<tr>
<td>Category</td>
<td>picklist</td>
<td>Acceso,PerdidaLlave,RoboLlave,RoboDoc</td>
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
<td>Soportes</td>
<td>relation</td>
<td>Soportes</td>
</tr>
<tr>
<td>Categoria</td>
<td>picklist</td>
<td>–None–</td>
</tr>
</tbody>
</table>

<br><br>
#### DESCRIPTION
<table class="table table-striped">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr>
<td>Description</td>
<td>text</td>
<td></td>
</tr>
</tbody>
</table>
