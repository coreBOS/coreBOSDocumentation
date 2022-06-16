---
title: 'State Court'
metadata:
    description: 'Module to record US State Courts'
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
Module to record US State Courts

===

### Fields

#### State Court Information

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
<td>State Court Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>State Court ID No</td>
<td>autonumber</td>
<td></td>
</tr>
<tr>
<td>Name of the State/Province</td>
<td>picklist</td>
<td></td>
</tr>
<tr>
<td>Court Address</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Name of the County</td>
<td>relation</td>
<td>County</td>
</tr>
<tr>
<td>Courthouse General Information</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>State Court Type</td>
<td>picklist</td>
<td></td>
</tr>
<tr>
<td>Courthouse Office and Service Directory</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Judicial Officer Name</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Court Calendar</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Judge</td>
<td>checkbox</td>
<td></td>
</tr>
<tr>
<td>ADR Information</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Assigned Judge</td>
<td>checkbox</td>
<td></td>
</tr>
<tr>
<td>Courthouse Juror Information</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Commissioner</td>
<td>checkbox</td>
<td></td>
</tr>
<tr>
<td>Local Forms</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Referee</td>
<td>checkbox</td>
<td></td>
</tr>
<tr>
<td>Local Rules</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Department,Room,Floor</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Tentative Rulings</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Courtroom Phone No</td>
<td>11</td>
<td></td>
</tr>
<tr>
<td>Court of Appeals</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Courthouse Main Phone No</td>
<td>11</td>
<td></td>
</tr>
<tr>
<td>Public Defender Information</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Clerk Phone</td>
<td>11</td>
<td></td>
</tr>
<tr>
<td>Court Website</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Other Phone</td>
<td>11</td>
<td></td>
</tr>
<tr>
<td>Email</td>
<td>email</td>
<td></td>
</tr>
<tr>
<td>Fax</td>
<td>11</td>
<td></td>
</tr>
<tr>
<td>Alternate Email</td>
<td>email</td>
<td></td>
</tr>
</tbody>
</table>
<br>
#### Driving Directions

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
<td>Driving Directions</td>
<td>url</td>
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
