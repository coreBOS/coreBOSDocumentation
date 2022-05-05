---
title: 'General Ledger Accounts'
metadata:
    description: 'General Ledger Accounts module.This is part of the Attorneys BackOffice accounting extensions.'
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

General Ledger Accounts module.
This is part of the Attorney's BackOffice **accounting extensions**.

===

### Fields

#### GL Account Information

<table class="table table-striped">
<thead>
<tr class="header">
<th>Field</th>
<th>Type</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>GL Account Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>GL Account Record No</td>
<td>autonumber</td>
<td></td>
</tr>
<tr class="odd">
<td>GL Account Code</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>GL Account Code 2</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>GL Account Group</td>
<td>relation</td>
<td>GLAGroups</td>
</tr>
<tr>
<td>Active GL Account</td>
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
<tr class="odd">
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
<tr class="odd">
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
<tr>
<td>Created Time</td>
<td>datetime</td>
<td></td>
</tr>
<tr class="odd">
<td>Modified Time</td>
<td>datetime</td>
<td></td>
</tr>
</tbody>
</table>