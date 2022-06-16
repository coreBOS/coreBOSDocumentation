---
title: 'Backup Procedure module'
metadata:
    description: 'This documentation-like module records all the backups systems and their responsible parties that are used in the account. Necessary for inventory knowledge and legal requirements.'
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
This documentation-like module records all the backups systems and their responsible parties that are used in the account. Necessary for inventory knowledge and legal requirements.

===

### Fields

#### Backup Information

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
<td>Backup No</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Procedure Name</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Account</td>
<td>relation</td>
<td>Accounts</td>
</tr>
<tr>
<td>Copied data</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Procedure description</td>
<td>text</td>
<td></td>
</tr>
<tr>
<td>Frequency</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Backup Location</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Person or area in charge of procedure</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Template</td>
<td>relation</td>
<td>Documents</td>
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