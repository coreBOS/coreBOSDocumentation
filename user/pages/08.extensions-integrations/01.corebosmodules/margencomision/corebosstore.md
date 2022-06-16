---
title: 'Commission Range module'
metadata:
    description: 'Module to register commission ranges. This module will permit you to record a start and end number associated to a commission, which can then be used in other modules to establish payments or similar.'
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
Module to register commission ranges. This module will permit you to record a start and end number associated to a commission, which can then be used in other modules to establish payments or similar.

===

### Fields

#### Commission Range Information

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
<td>Range Start</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Range Group</td>
<td>picklist</td>
<td></td>
</tr>
<tr>
<td>Range End</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>CommissionRange No</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Commission</td>
<td>number</td>
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
