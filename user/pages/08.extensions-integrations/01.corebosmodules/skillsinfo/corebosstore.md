---
title: 'Skills and Talents Information'
metadata:
    description: 'Skills information module to register information about the skills and talents of your employees and contacts.This is part of the Attorneys Back Office Human Resources extensions.'
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
Skills information module to register information about the skills and talents of your employees and contacts.
This is part of the **Attorney's Back Office Human Resources** extensions.

===

### Fields

#### Skill Information

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
<td>Related to</td>
<td>relation</td>
<td>Attorneys,Managers,Paralegals,Secretaries,SupportPersonnel,Procurador</td>
</tr>
<tr>
<td>Years of Experience</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Skill Type</td>
<td>picklist</td>
<td>--- Please Select ---,Ability To Work With Little Supervision,
Ability To Work With No Supervision,Active Learning ,Active Listening ,
Administering Programs,Administration Support,...,Writing Reports,Writing Skills</td>
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
<td>Skill Reference</td>
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
