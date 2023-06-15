---
title: 'Adequacy: Flow module'
metadata:
    description: 'This module is part of the Adequacy functionality. It represents a pool of steps or actions that can be done in any given adequacy project. The flow module will group these steps together into sequences to be used.'
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

This module is part of the [Adequacy functionality](../../01.corebosmodules/adecuaciones/id:d51886e9ff11c8667ddda0973c2757e8/store:corebosmodule). It represents a pool of steps or actions that can be done in any given adequacy project. The [flow](../../01.corebosmodules/flujo/id:5a98bef1ee218c8c1b1bb13ddbcce1e8/store:corebosmodule) module will group these steps together into sequences to be used.

===

### Fields

#### Step Information

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
<td>Required</td>
<td>checkbox</td>
<td></td>
</tr>
<tr>
<td>Duration</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Template</td>
<td>relation</td>
<td>Documents</td>
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
</tbody>
</table>
<br>
#### Custom Information
<br>
#### Step Information

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
