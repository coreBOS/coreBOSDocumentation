---
title: 'Work Experience'
metadata:
    description: 'Work Experience module to register information about the employment history of your employees and contacts.This is part of the Attorneys Back Office Human Resources extensions.'
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

Work Experience module to register information about the employment history of your employees and contacts.
This is part of the **Attorney's Back Office Human Resources** extensions.

===

### Fields

#### Work Experience Information

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
<td>Person</td>
<td>relation</td>
<td>Attorneys,Managers,Paralegals,Secretaries,SupportPersonnel,Procurador</td>
</tr>
<tr>
<td>Job Title</td>
<td>relation</td>
<td>JobTitle</td>
</tr>
<tr>
<td>Company Name</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Worked from</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Industry</td>
<td>picklist</td>
<td></td>
</tr>
<tr>
<td>Worked to</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Company Address. Supervisor Name</td>
<td>text</td>
<td></td>
</tr>
<tr>
<td>Number of years</td>
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
<td>Work Experience No</td>
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
