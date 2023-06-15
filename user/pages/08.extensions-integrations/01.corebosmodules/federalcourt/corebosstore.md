---
title: 'Federal Court'
metadata:
    description: 'Module to record US Federal Courts'
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

Module to record US Federal Courts

===

### Fields

#### Federal Court and Courtroom Information

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
<td>Federal Court Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Court Record ID No</td>
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
<td>U.S. Appeals Court Circuit Name</td>
<td>relation</td>
<td>USAppealsCourtCircuit</td>
</tr>
<tr>
<td>Federal Court Type</td>
<td>picklist</td>
<td>--- Please Select ---,Bankruptcy Court,Court of Appeals,
Court of Federal Claims,Court of International Trade,Court of Veterans Appeals,
District Court,Federal Administrative Agencies and Boards,
Military Courts (Trial and Appellate),Supreme Court,Tax Court</td>
</tr>
<tr>
<td>District Judge</td>
<td>checkbox</td>
<td></td>
</tr>
<tr>
<td>U.S. District Name</td>
<td>relation</td>
<td>USFederalDistricts</td>
</tr>
<tr>
<td>Senior District Judge</td>
<td>checkbox</td>
<td></td>
</tr>
<tr>
<td>Judicial Officer Name</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Assigned Judge</td>
<td>checkbox</td>
<td></td>
</tr>
<tr>
<td>Name of the Referring Judge</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Chief Magistrate Judge</td>
<td>checkbox</td>
<td></td>
</tr>
<tr>
<td>Department,Room,Floor</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Magistrate Judge</td>
<td>checkbox</td>
<td></td>
</tr>
<tr>
<td>Court Clerk</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Presiding Judge</td>
<td>checkbox</td>
<td></td>
</tr>
<tr>
<td>Court Reporter</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Name of the Presiding Judge</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Courtroom Phone No</td>
<td>11</td>
<td></td>
</tr>
<tr>
<td>Referring Judge</td>
<td>checkbox</td>
<td></td>
</tr>
<tr>
<td>Courthouse Main Phone No</td>
<td>11</td>
<td></td>
</tr>
<tr>
<td>Electronic Filing Email</td>
<td>email</td>
<td></td>
</tr>
<tr>
<td>Clerk Phone</td>
<td>11</td>
<td></td>
</tr>
<tr>
<td>Alternate Email</td>
<td>email</td>
<td></td>
</tr>
<tr>
<td>Court Report Phone</td>
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
<td>Courtroom Motion Calendar</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Fax</td>
<td>11</td>
<td></td>
</tr>
<tr>
<td>Driving Directions</td>
<td>url</td>
<td></td>
</tr>
</tbody>
</table>
<br>
#### Courthouse Information

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
<td>Courthouse General Information</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Courthouse Juror Information</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Courthouse Office and Service Directory</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Tentative Rulings</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Local Forms</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>ADR Information</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Local Rules</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Clerk Office Services</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Attorney Admissions</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Attorney Admissions Search</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Attorney Assistance</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Services for Attorney</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Criminal Justice Act Information</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Criminal Duty Calendar</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Master Calendar</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Motion Calendar</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>PIA Calendar</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>PACER Information</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Filing Procedures</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>General Orders</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Judges Procedures and Schedules</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Notices from the Clerk</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Pro Bono Panel</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Recently Issued Opinions and Orders</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Court Rosters and Duty Schedules</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>NARA Inquiry</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Courthouse Parking Information</td>
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