---
title: 'Relationships Module'
metadata:
    description: 'Module to register the relation between two accounts, contacts, vendors or leads.The module enables you to record and analyze relationships of a lead, an account or a contact for a better understanding of its roles, dependencies and influences.'
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
Module to register the relation between two accounts, contacts, vendors or leads.
The module enables you to record and analyze relationships of a lead, an account or a contact for a better understanding of its roles, dependencies and influences.

===

### Fields

#### Relationship Information

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
<td>Actor A</td>
<td>relation</td>
<td>Accounts,Contacts,Vendors,Leads</td>
</tr>
<tr>
<td>Relation Start</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Actor B</td>
<td>relation</td>
<td>Accounts,Contacts,Vendors,Leads</td>
</tr>
<tr>
<td>Relation End</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Relation Type</td>
<td>picklist</td>
<td>Network,Supplier,Family,Work</td>
</tr>
<tr>
<td>Relation No</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Relation Status</td>
<td>picklist</td>
<td>Active,Inactive</td>
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
