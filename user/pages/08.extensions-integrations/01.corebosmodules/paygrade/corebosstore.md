---
title: 'Pay Grades Module'
metadata:
    description: 'This module registers the different payment ranges our company works with and permits relating our staff with each one.This is part of the Attorneys Back Office Human Resources extensions.'
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

This module registers the different payment ranges our company works with and permits relating our staff with each one.
This is part of the **Attorney's Back Office Human Resources** extensions.

===

### Fields

#### Pay Grade Record Information

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
<td>Pay Grade Code Name</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Pay Grade Code ID</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Minimum Salary</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Maximum Salary</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Step Increase</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Pay Grade No</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
</tr>
</tbody>
</table>
<br>
#### Custom Information
<br>
#### Comments

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
#### Additional Record Information

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
