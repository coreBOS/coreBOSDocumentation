---
title: 'Adequacy: Flow module'
metadata:
    description: 'This module is part of the Adequacy functionality. It represents the exact sequence of steps that must be taken to achieve the implementation process in the company. The idea of this module is to permit creating as many business process flow as needed and then instantiate then using an Adequacy. A business flow is an exact sequence of business steps.'
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
This module is part of the [Adequacy functionality](../../01.corebosmodules/adecuaciones/id:d51886e9ff11c8667ddda0973c2757e8/store:corebosmodule). It represents the exact sequence of steps that must be taken to achieve the implementation process in the company. The idea of this module is to permit creating as many business process flow as needed and then instantiate then using [Adequacy](../../01.corebosmodules/adecuaciones/id:d51886e9ff11c8667ddda0973c2757e8/store:corebosmodule). A business flow is an exact sequence of [business steps](../../01.corebosmodules/pasos/id:e8a8b14fbef3ee9d0e6fd9d76475b64f/store:corebosmodule).

===

### Fields

#### WorkFlow Information

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
<td>Estado</td>
<td>picklist</td>
<td>—–,Vigente,Obsoleto</td>
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
</tbody>
</table>
<br>
#### Custom Information
<br>
#### Description Information

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
