---
title: 'Session/Event Details Information'
metadata:
    description: 'Module to register the fact of a session of some event that will take place (related with cbAttendance module)'
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
Module to register the fact of a session of some event that will take place (related with [cbAttendance](../../01.corebosmodules/cbattendance/id:c96a81e3711333dc402b58e7a289cb12/store:corebosmodule) module).

===

### Fields

#### Session Information

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
<td>Session No</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Session Name</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Course</td>
<td>relation</td>
<td>cbTraining</td>
</tr>
<tr>
<td>Date Start</td>
<td>datedate</td>
<td></td>
</tr>
<tr>
<td>Time Start</td>
<td>14</td>
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
