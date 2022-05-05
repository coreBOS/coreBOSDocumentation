---
title: 'Work Schedule Module'
metadata:
    description: 'Module to record the different weekly hours that we work in the office.This is part of the Attorneys Back Office extensions.'
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

Module to record the different weekly hours that we work in the office.
This is part of the **Attorney's Back Office** extensions.

===

### Fields

#### Work Schedule Information

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
<td>Work Schedule Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Work Schedule No</td>
<td>autonumber</td>
<td></td>
</tr>
<tr>
<td>Work Schedule for</td>
<td>relation</td>
<td>Attorneys,Managers,Paralegals,Secretaries,SupportPersonnel,Procurador</td>
</tr>
<tr>
<td>Works on weekends</td>
<td>checkbox</td>
<td></td>
</tr>
<tr>
<td>Year</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Default</td>
<td>checkbox</td>
<td></td>
</tr>
<tr>
<td>Active</td>
<td>checkbox</td>
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
#### Schedule

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
<td>Monday Morning Start</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Monday Afternoon Start</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Monday Morning End</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Monday Afternoon End</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Tuesday Morning Start</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Tuesday Afternoon Start</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Tuesday Morning End</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Tuesday Afternoon End</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Wednesday Morning Start</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Wednesday Afternoon Start</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Wednesday Morning End</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Wednesday Afternoon End</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Thursday Morning Start</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Thursday Afternoon Start</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Thursday Morning End</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Thursday Afternoon End</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Friday Morning Start</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Friday Afternoon Start</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Friday Morning End</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Friday Afternoon End</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Saturday Morning Start</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Saturday Afternoon Start</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Saturday Morning End</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Saturday Afternoon End</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Sunday Morning Start</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Sunday Afternoon Start</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Sunday Morning End</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Sunday Afternoon End</td>
<td>number</td>
<td></td>
</tr>
</tbody>
</table>
<br>
#### Holidays

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
<td>January</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>February</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>March</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>April</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>May</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>June</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>July</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>August</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>September</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>October</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>November</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>December</td>
<td>string</td>
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
