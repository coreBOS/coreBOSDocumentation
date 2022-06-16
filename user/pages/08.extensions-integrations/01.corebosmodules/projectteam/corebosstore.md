---
title: 'Project Team'
metadata:
    description: 'Module to relate project and contacts. It is similar to the Stake Holder module.'
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
Module to relate project and contacts. It is similar to the [Stake Holder module](../../01.corebosmodules/cbstakeholder/id:76ca3874026d767b20a2406c4989c498/store:corebosmodule).

===

### Fields

#### Team Information

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
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Function</td>
<td>picklist</td>
<td></td>
</tr>
<tr>
<td>Related Project</td>
<td>relation</td>
<td>Project</td>
</tr>
<tr>
<td>Resource</td>
<td>relation</td>
<td>Contacts</td>
</tr>
<tr>
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
<tr>
<td>Project Team No</td>
<td>autonumber</td>
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
<td>Last Modified By</td>
<td>52</td>
<td></td>
</tr>
<tr>
<td>Created By</td>
<td>52</td>
<td></td>
</tr>
</tbody>
</table>
<br>

### Description Information

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
<td>Comment</td>
<td>text</td>
<td></td>
</tr>
</tbody>
</table>
