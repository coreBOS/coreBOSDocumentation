---
title: 'Users Working on Projects'
metadata:
    description: 'This module permits relating users to different projects in the system. It is a very basic team management module.This is part of the Attorneys Back Office Human Resources extensions.'
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

This module permits relating users to different projects in the system. It is a very basic team management module.
This is part of the **Attorney's Back Office Human Resources** extensions.

===

### Fields

#### User Works In Information

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
<td>Litigation Team</td>
<td>relation</td>
<td>LitigationTeam</td>
</tr>
<tr>
<td>User</td>
<td>101</td>
<td></td>
</tr>
<tr>
<td>Function-Responsibility</td>
<td>relation</td>
<td>LTFunctions</td>
</tr>
<tr>
<td>Function-Responsibility Priority</td>
<td>picklist</td>
<td></td>
</tr>
<tr>
<td>Function-Responsibility Status</td>
<td>picklist</td>
<td></td>
</tr>
<tr>
<td>User-Team No</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
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
