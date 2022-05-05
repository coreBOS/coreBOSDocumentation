---
title: 'Dependents'
metadata:
    description: 'Contact like module related to Contacts where you can save information about people that depend upon the main Contact.'
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

Contact like module related to Contacts where you can save information about people that depend upon the main Contact.

===

### Fields

#### Dependent Information

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
<td>Parent or Legal guardian</td>
<td>relation</td>
<td>Attorneys,Managers,Paralegals,Secretaries,SupportPersonnel</td>
</tr>
<tr>
<td>First, Last Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Relationship</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Date of Birth</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Lives at same address</td>
<td>checkbox</td>
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
<td>Dependent No</td>
<td>autonumber</td>
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