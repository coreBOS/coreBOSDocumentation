---
title: 'Research Request Actions module'
metadata:
    description: 'This module is related with Research Request module and details the different actions or steps taken to resolve or attend the request'
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

This module is related with [Research Request module](../../01.corebosmodules/researchrequest/id:5a49190bde7baeebdc60cde9dc28f9b5/store:corebosmodule) and details the different actions or steps taken to resolve or attend the request.

===

### Fields

#### Research Request Actions Information

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
<td>Research Request</td>
<td>relation</td>
<td>ResearchRequest</td>
</tr>
<tr>
<td>RR Actions No</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Expide</td>
<td>101</td>
<td></td>
</tr>
<tr>
<td>Version</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Fecha Entrega</td>
<td>date</td>
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
