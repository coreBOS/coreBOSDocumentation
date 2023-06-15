---
title: 'Outsourcing Module'
metadata:
    description: 'Contact-like module to register information about outsourced third party people or teams working on our projects.This is part of the Attorneys Back Office Human Resources extensions.'
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

Contact-like module to register information about outsourced third party people or teams working on our projects.
This is part of the **Attorney's Back Office Human Resources** extensions.

===

### Fields

#### Outsourcing Information

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
<td>Vendor</td>
<td>relation</td>
<td>Vendors</td>
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
<td>Outsourcing No</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
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
<br>
#### Additional Information

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
