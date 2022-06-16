---
title: 'Quality Claims module'
metadata:
    description: 'Module to control Quality Claims, used to enforce and document ISO standards. It should capture the details of the claim, who is attending it, the date references and the outcome. This module is related with Quality Actions module where each exact step is recorded.'
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
Module to control Quality Claims, used to enforce and document ISO standards. It should capture the details of the claim, who is attending it, the date references and the outcome. This module is related with [Quality Actions module](../../01.corebosmodules/qualityactions/id:61447d2f5490fd70eeed1fa95a0ddf6e/store:corebosmodule) where each exact step is recorded.


===

### Fields

#### Quality Claims Information

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
<td>Account Name</td>
<td>relation</td>
<td>Accounts</td>
</tr>
<tr>
<td>Nº de Pedido</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Entidad Relacionada</td>
<td>relation</td>
<td>Project,HelpDesk</td>
</tr>
<tr>
<td>Claim Status</td>
<td>picklist</td>
<td>--None--</td>
</tr>
<tr>
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
<tr>
<td>Claim Priority</td>
<td>picklist</td>
<td>Low,Medium,High</td>
</tr>
<tr>
<td>Emitting Department</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Claim Type</td>
<td>picklist</td>
<td>--None--</td>
</tr>
<tr>
<td>Responsible</td>
<td>101</td>
<td></td>
</tr>
<tr>
<td>Claim Date</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Receiving Department</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Quality Claim No</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
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
#### Description

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
