---
title: 'Cookies module'
metadata:
    description: 'This asset-like module records all the cookies being used by an account on their website. Necessary for inventory knowledge and legal requirements.'
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

This asset-like module records all the cookies being used by an account on their website. Necessary for inventory knowledge and legal requirements.

===

### Fields

#### LBL_COOKIES_INFORMATION

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
<td>cookie_no</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>cookie_tipo</td>
<td>picklist</td>
<td>—,Sesion,Permanente,De funcionalidad,Terceros,Analiticas,Otros
</td>
</tr>
<tr>
<td>cookie</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>cookie_finalidad</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>cookie_caducidad</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>cookie_propietario</td>
<td>string</td>
<td></td>
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
<br>
#### Custom Information