---
title: 'Work Schedule Module'
---

Work Schedule Module
====================

Module to record the different weekly hours that we work in the
office.  
This is part of the **Attorney's Back Office** extensions.  
---- dataentry ---- name : tsolucio/WorkSchedule type : corebos-module
description\_wiki: Module to record the different weekly hours that we
work in the office.  
This is part of the **Attorney's Back Office** extensions.
keywords\_tags : work,schedule,timetable version : 1.0 homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:workschedule>
release\_dt : 2013-06-12 licenses : Vizsage distribution : Subscription
authorname : JPL TSolucio, S.L. authoremail\_mail :
info(at)tsolucio(dot)com supportemail\_mail : info(at)tsolucio(dot)com
supportissues\_url : \[subscription Contract\] supportsource\_url :
\[subscription URI\]/WorkSchedule.git

------------------------------------------------------------------------

  

Fields
======

### Work Schedule Information

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
<td>Work Schedule Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr class="even">
<td>Work Schedule No</td>
<td>autonumber</td>
<td></td>
</tr>
<tr class="odd">
<td>Work Schedule for</td>
<td>relation</td>
<td>Attorneys,Managers,Paralegals,Secretaries,SupportPersonnel,Procurador</td>
</tr>
<tr class="even">
<td>Works on weekends</td>
<td>checkbox</td>
<td></td>
</tr>
<tr class="odd">
<td>Year</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Default</td>
<td>checkbox</td>
<td></td>
</tr>
<tr class="odd">
<td>Active</td>
<td>checkbox</td>
<td></td>
</tr>
<tr class="even">
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
</tbody>
</table>

### Schedule

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
<td>Monday Morning Start</td>
<td>number</td>
<td></td>
</tr>
<tr class="even">
<td>Monday Afternoon Start</td>
<td>number</td>
<td></td>
</tr>
<tr class="odd">
<td>Monday Morning End</td>
<td>number</td>
<td></td>
</tr>
<tr class="even">
<td>Monday Afternoon End</td>
<td>number</td>
<td></td>
</tr>
<tr class="odd">
<td>Tuesday Morning Start</td>
<td>number</td>
<td></td>
</tr>
<tr class="even">
<td>Tuesday Afternoon Start</td>
<td>number</td>
<td></td>
</tr>
<tr class="odd">
<td>Tuesday Morning End</td>
<td>number</td>
<td></td>
</tr>
<tr class="even">
<td>Tuesday Afternoon End</td>
<td>number</td>
<td></td>
</tr>
<tr class="odd">
<td>Wednesday Morning Start</td>
<td>number</td>
<td></td>
</tr>
<tr class="even">
<td>Wednesday Afternoon Start</td>
<td>number</td>
<td></td>
</tr>
<tr class="odd">
<td>Wednesday Morning End</td>
<td>number</td>
<td></td>
</tr>
<tr class="even">
<td>Wednesday Afternoon End</td>
<td>number</td>
<td></td>
</tr>
<tr class="odd">
<td>Thursday Morning Start</td>
<td>number</td>
<td></td>
</tr>
<tr class="even">
<td>Thursday Afternoon Start</td>
<td>number</td>
<td></td>
</tr>
<tr class="odd">
<td>Thursday Morning End</td>
<td>number</td>
<td></td>
</tr>
<tr class="even">
<td>Thursday Afternoon End</td>
<td>number</td>
<td></td>
</tr>
<tr class="odd">
<td>Friday Morning Start</td>
<td>number</td>
<td></td>
</tr>
<tr class="even">
<td>Friday Afternoon Start</td>
<td>number</td>
<td></td>
</tr>
<tr class="odd">
<td>Friday Morning End</td>
<td>number</td>
<td></td>
</tr>
<tr class="even">
<td>Friday Afternoon End</td>
<td>number</td>
<td></td>
</tr>
<tr class="odd">
<td>Saturday Morning Start</td>
<td>number</td>
<td></td>
</tr>
<tr class="even">
<td>Saturday Afternoon Start</td>
<td>number</td>
<td></td>
</tr>
<tr class="odd">
<td>Saturday Morning End</td>
<td>number</td>
<td></td>
</tr>
<tr class="even">
<td>Saturday Afternoon End</td>
<td>number</td>
<td></td>
</tr>
<tr class="odd">
<td>Sunday Morning Start</td>
<td>number</td>
<td></td>
</tr>
<tr class="even">
<td>Sunday Afternoon Start</td>
<td>number</td>
<td></td>
</tr>
<tr class="odd">
<td>Sunday Morning End</td>
<td>number</td>
<td></td>
</tr>
<tr class="even">
<td>Sunday Afternoon End</td>
<td>number</td>
<td></td>
</tr>
</tbody>
</table>

### Holidays

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
<td>January</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>February</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>March</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>April</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>May</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>June</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>July</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>August</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>September</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>October</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>November</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>December</td>
<td>string</td>
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
<td>Created Time</td>
<td>datetime</td>
<td></td>
</tr>
<tr class="even">
<td>Modified Time</td>
<td>datetime</td>
<td></td>
</tr>
</tbody>
</table>
