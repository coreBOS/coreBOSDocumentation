---
title: 'Adequacy module'
metadata:
    description: 'Implementation process in the company designated by the flow and steps modules'
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

### Fields

#### Adequations Information

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
<td>Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Start Date</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>End Date</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>State</td>
<td>picklist</td>
<td>-----,Terminado</td>
</tr>
<tr>
<td>Paso Actual</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>% Realizacion</td>
<td>number</td>
<td></td>
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
<td>Flujo de Trabajo</td>
<td>relation</td>
<td>Flujo</td>
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

#### Adequations Description

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
<td>Description</td>
<td>text</td>
<td></td>
</tr>
</tbody>
</table>
