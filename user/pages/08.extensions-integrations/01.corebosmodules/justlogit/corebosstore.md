---
title: 'Just Log It module'
metadata:
    description: 'An Event/Calendar type module to register things that happen, incidents worth recording or simply time spent on some task.'
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

An Event/Calendar type module to register things that happen, incidents worth recording or simply time spent on some task.

===

### Fields

#### Just Log It Information

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
<td>Date</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Log No</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Time</td>
<td>time</td>
<td></td>
</tr>
<tr>
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
<tr>
<td>Event</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Created Time</td>
<td>datetime</td>
<td></td>
</tr>
<tr>
<td>Value</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Modified Time</td>
<td>datetime</td>
<td></td>
</tr>
<tr>
<td>Related To</td>
<td>relation</td>
<td></td>
</tr>
<tr>
<td>Related Module</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Done From</td>
<td>string</td>
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
