---
title: 'Federal Court'
---

Federal Court
=============

Module to record US Federal Courts  
---- dataentry ---- name : tsolucio/FederalCourt type : corebos-module
description\_wiki: Module to record US Federal Courts  
keywords\_tags : ABO,Attorney Back Office,court version : 1.0
homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:federalcourt>
release\_dt : 2013-06-12 licenses : Vizsage price: 150eur buyemail\_mail
: paypal(at)tsolucio(dot)com distribution : Sale authorname : JPL
TSolucio, S.L. authoremail\_mail : info(at)tsolucio(dot)com
supportemail\_mail : info(at)tsolucio(dot)com

------------------------------------------------------------------------

  

Fields
======

### Federal Court and Courtroom Information

<table>
<thead>
<tr class="header">
<th>Field</th>
<th>Type</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Federal Court Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr class="even">
<td>Court Record ID No</td>
<td>autonumber</td>
<td></td>
</tr>
<tr class="odd">
<td>Name of the State/Province</td>
<td>picklist</td>
<td></td>
</tr>
<tr class="even">
<td>Court Address</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>Name of the County</td>
<td>relation</td>
<td>County</td>
</tr>
<tr class="even">
<td>U.S. Appeals Court Circuit Name</td>
<td>relation</td>
<td>USAppealsCourtCircuit</td>
</tr>
<tr class="odd">
<td>Federal Court Type</td>
<td>picklist</td>
<td>--- Please Select ---,Bankruptcy Court,Court of Appeals,Court of Federal Claims,Court of International Trade,Court of Veterans Appeals,District Court,Federal Administrative Agencies and Boards,Military Courts (Trial and Appellate),Supreme Court,Tax Court</td>
</tr>
<tr class="even">
<td>District Judge</td>
<td>checkbox</td>
<td></td>
</tr>
<tr class="odd">
<td>U.S. District Name</td>
<td>relation</td>
<td>USFederalDistricts</td>
</tr>
<tr class="even">
<td>Senior District Judge</td>
<td>checkbox</td>
<td></td>
</tr>
<tr class="odd">
<td>Judicial Officer Name</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Assigned Judge</td>
<td>checkbox</td>
<td></td>
</tr>
<tr class="odd">
<td>Name of the Referring Judge</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Chief Magistrate Judge</td>
<td>checkbox</td>
<td></td>
</tr>
<tr class="odd">
<td>Department,Room,Floor</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Magistrate Judge</td>
<td>checkbox</td>
<td></td>
</tr>
<tr class="odd">
<td>Court Clerk</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Presiding Judge</td>
<td>checkbox</td>
<td></td>
</tr>
<tr class="odd">
<td>Court Reporter</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Name of the Presiding Judge</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>Courtroom Phone No</td>
<td>11</td>
<td></td>
</tr>
<tr class="even">
<td>Referring Judge</td>
<td>checkbox</td>
<td></td>
</tr>
<tr class="odd">
<td>Courthouse Main Phone No</td>
<td>11</td>
<td></td>
</tr>
<tr class="even">
<td>Electronic Filing Email</td>
<td>email</td>
<td></td>
</tr>
<tr class="odd">
<td>Clerk Phone</td>
<td>11</td>
<td></td>
</tr>
<tr class="even">
<td>Alternate Email</td>
<td>email</td>
<td></td>
</tr>
<tr class="odd">
<td>Court Report Phone</td>
<td>11</td>
<td></td>
</tr>
<tr class="even">
<td>Court Website</td>
<td>url</td>
<td></td>
</tr>
<tr class="odd">
<td>Other Phone</td>
<td>11</td>
<td></td>
</tr>
<tr class="even">
<td>Courtroom Motion Calendar</td>
<td>url</td>
<td></td>
</tr>
<tr class="odd">
<td>Fax</td>
<td>11</td>
<td></td>
</tr>
<tr class="even">
<td>Driving Directions</td>
<td>url</td>
<td></td>
</tr>
</tbody>
</table>

### Courthouse Information

<table>
<thead>
<tr class="header">
<th>Field</th>
<th>Type</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Courthouse General Information</td>
<td>url</td>
<td></td>
</tr>
<tr class="even">
<td>Courthouse Juror Information</td>
<td>url</td>
<td></td>
</tr>
<tr class="odd">
<td>Courthouse Office and Service Directory</td>
<td>url</td>
<td></td>
</tr>
<tr class="even">
<td>Tentative Rulings</td>
<td>url</td>
<td></td>
</tr>
<tr class="odd">
<td>Local Forms</td>
<td>url</td>
<td></td>
</tr>
<tr class="even">
<td>ADR Information</td>
<td>url</td>
<td></td>
</tr>
<tr class="odd">
<td>Local Rules</td>
<td>url</td>
<td></td>
</tr>
<tr class="even">
<td>Clerk Office Services</td>
<td>url</td>
<td></td>
</tr>
<tr class="odd">
<td>Attorney Admissions</td>
<td>url</td>
<td></td>
</tr>
<tr class="even">
<td>Attorney Admissions Search</td>
<td>url</td>
<td></td>
</tr>
<tr class="odd">
<td>Attorney Assistance</td>
<td>url</td>
<td></td>
</tr>
<tr class="even">
<td>Services for Attorney</td>
<td>url</td>
<td></td>
</tr>
<tr class="odd">
<td>Criminal Justice Act Information</td>
<td>url</td>
<td></td>
</tr>
<tr class="even">
<td>Criminal Duty Calendar</td>
<td>url</td>
<td></td>
</tr>
<tr class="odd">
<td>Master Calendar</td>
<td>url</td>
<td></td>
</tr>
<tr class="even">
<td>Motion Calendar</td>
<td>url</td>
<td></td>
</tr>
<tr class="odd">
<td>PIA Calendar</td>
<td>url</td>
<td></td>
</tr>
<tr class="even">
<td>PACER Information</td>
<td>url</td>
<td></td>
</tr>
<tr class="odd">
<td>Filing Procedures</td>
<td>url</td>
<td></td>
</tr>
<tr class="even">
<td>General Orders</td>
<td>url</td>
<td></td>
</tr>
<tr class="odd">
<td>Judges Procedures and Schedules</td>
<td>url</td>
<td></td>
</tr>
<tr class="even">
<td>Notices from the Clerk</td>
<td>url</td>
<td></td>
</tr>
<tr class="odd">
<td>Pro Bono Panel</td>
<td>url</td>
<td></td>
</tr>
<tr class="even">
<td>Recently Issued Opinions and Orders</td>
<td>url</td>
<td></td>
</tr>
<tr class="odd">
<td>Court Rosters and Duty Schedules</td>
<td>url</td>
<td></td>
</tr>
<tr class="even">
<td>NARA Inquiry</td>
<td>url</td>
<td></td>
</tr>
<tr class="odd">
<td>Courthouse Parking Information</td>
<td>url</td>
<td></td>
</tr>
</tbody>
</table>

### Custom Information

### Description

<table>
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

### Additional Information

<table>
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
<tr class="even">
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
