---
title: 'Training Details Information'
metadata:
    description: 'Module to record the registration of contacts to and the service price of an event that will take place (related with cbAttendance module)'
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

Module to record the registration of contacts to and the service price of an event that will take place (related with cbAttendance module)

===

### Fields

#### Training Information

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
<td>Training No</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Service</td>
<td>relation</td>
<td>Services</td>
</tr>
<tr>
<td>Training Status</td>
<td>picklist</td>
<td>Active,Not active,Suspended,Canceled</td>
</tr>
<tr>
<td>Location</td>
<td>picklist</td>
<td>-</td>
</tr>
<tr>
<td>Date Start</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Date End</td>
<td>date</td>
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
