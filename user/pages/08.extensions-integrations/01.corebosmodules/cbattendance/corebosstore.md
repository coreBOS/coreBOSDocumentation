---
title: 'Attendance Details Information'
metadata:
    description: 'Module to register the fact of a contact assisting an event or session (related with cbSession module)'
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

Module to register the fact of a contact assisting an event or session (related with [cbSession](../../01.corebosmodules/cbsession/id:1a493a6456d9f38c3bb1aeecf3d9a1ab/store:corebosmodule) module).

===

### Fields

#### Attendance Information

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
<td>Attendance No</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Session</td>
<td>relation</td>
<td>cbSession</td>
</tr>
<tr>
<td>Student</td>
<td>relation</td>
<td>Contacts</td>
</tr>
<tr>
<td>Assist?</td>
<td>checkbox</td>
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
