---
title: 'ARCO module'
metadata:
    description: 'Acceso, Rectificación, Cancelación y Oposición'
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

### Fields

#### ARCO Information

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
<td>Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Account</td>
<td>relation</td>
<td>Accounts</td>
</tr>
<tr>
<td>Type</td>
<td>picklist</td>
<td>Acceso,Rectificacion,Cancelacion,Oposicion</td>
</tr>
<tr>
<td>Representation</td>
<td>picklist</td>
<td>Propio Interesado,Representante legal</td>
</tr>
<tr>
<td>Petition</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Address</td>
<td>text</td>
<td></td>
</tr>
<tr>
<td>Date</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Exercice Status</td>
<td>picklist</td>
<td>Pendiente de atencion,Atendido</td>
</tr>
<tr>
<td>Access Status</td>
<td>picklist</td>
<td>Registrado,Solicitada concrecion,Resuelta solicitud</td>
</tr>
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
</tbody>
</table>
