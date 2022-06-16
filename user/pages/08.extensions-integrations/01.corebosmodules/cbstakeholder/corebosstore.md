---
title: 'Stake Holder Information'
metadata:
    description: 'Module to register the relation between accounts, contacts, vendors or leads against project or tickets. Representing their interest as stake holders on the project or ticket.'
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
Module to register the relation between accounts, contacts, vendors or leads against project or tickets. Representing their interest as stake holders on the project or ticket.

===

### Fields

#### StakeHolder Information

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
<td>StakeHolder</td>
<td>relation</td>
<td>Accounts,Contacts,Vendors,Leads</td>
</tr>
<tr>
<td>Participation Start</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Related To</td>
<td>relation</td>
<td>Project,HelpDesk</td>
</tr>
<tr>
<td>Participation End</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Participation Type</td>
<td>picklist</td>
<td>Network,Supplier,Family,Work</td>
</tr>
<tr>
<td>StakeHolder No</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Participation Status</td>
<td>picklist</td>
<td>Activo,Inactivo</td>
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
