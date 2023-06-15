---
title: 'Register Backups module'
metadata:
    description: 'This module records all the backups that have been done. Necessary for inventory knowledge and legal requirements.'
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

This module records all the backups that have been done. Necessary for inventory knowledge and legal requirements.

===

### Fields

#### Incident Information

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
<td>Assigned To</td>
<td>assigned to</td>
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
<td>Description</td>
<td>text</td>
<td></td>
</tr>
<tr>
<td>Identificacion</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Frecuencia</td>
<td>picklist</td>
<td>No,Diaria,Semanal,Quincenal,Semanas Pares,Semanas Impares,Mensual,Trimestral,Anual</td>
</tr>
<tr>
<td>ProcedimientoRealizacion</td>
<td>text</td>
<td></td>
</tr>
<tr>
<td>ProcedimientoRecuperacion</td>
<td>text</td>
<td></td>
</tr>
<tr>
<td>Ubicacion</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>UsuariosAutorizados</td>
<td>relation</td>
<td>Empleados,Contacts,Vendors</td>
</tr>
<tr>
<td>Title</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Account</td>
<td>relation</td>
<td>Accounts</td>
</tr>
<tr>
<td>StartTime</td>
<td>datetime (internal)</td>
<td></td>
</tr>
<tr>
<td>Nodisponible</td>
<td>checkbox</td>
<td></td>
</tr>
<tr>
<td>Plantilla</td>
<td>relation</td>
<td>Documents</td>
</tr>
<tr>
<td>execProc</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>CopiaCifrada</td>
<td>picklist</td>
<td>Si,No</td>
</tr>
<tr>
<td>Soportes</td>
<td>relation</td>
<td>Soportes</td>
</tr>
<tr>
<td>Fichero</td>
<td>relation</td>
<td>Fichero</td>
</tr>
</tbody>
</table>
<br>
#### Description Information

#### Solution Information
