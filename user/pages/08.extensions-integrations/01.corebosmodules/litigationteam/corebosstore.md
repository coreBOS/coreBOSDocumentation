---
title: 'Litigation Team Details'
metadata:
    description: 'This module permits defining the details and people working on a litigation. It is a very basic team management module.This is part of the Attorneys Back Office extensions.'
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
This module permits defining the details and people working on a litigation. It is a very basic team management module.
This is part of the **Attorney's Back Office** extensions.

===

### Fields

#### Litigation Team Information

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
<td>Team Name/Description</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Litigation Team No</td>
<td>autonumber</td>
<td></td>
</tr>
<tr>
<td>Matter Related to</td>
<td>relation</td>
<td>Accounts,Contacts</td>
</tr>
<tr>
<td>Function-Responsibility</td>
<td>relation</td>
<td>LTFunctions</td>
</tr>
<tr>
<td>Function/Responsibility Execution Priority</td>
<td>picklist</td>
<td>--- Please Select ---,Low,Medium,High,Urgent</td>
</tr>
<tr>
<td>Function/Responsibility Execution Status</td>
<td>picklist</td>
<td>--- Please Select ---,10%,20%,30%,40%,50%,60%,70%,80%,90%,100%</td>
</tr>
<tr>
<td>Team Leader</td>
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
