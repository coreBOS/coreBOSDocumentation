---
title: 'Session/Event Details Information'
---

Session/Event Details Information
=================================

Module to register the fact of a session of some event that will take
place (related with [cbAttendance
module](http://corebos.org/documentation/doku.php?id=en:extensions:extensions:cbattendance))  
---- dataentry ---- name : tsolucio/cbSession type : corebos-module
description\_wiki: Module to register the fact of a session of some
event that will take place (related with [cbAttendance
module](http://corebos.org/documentation/doku.php?id=en:extensions:extensions:cbattendance))
keywords\_tags : hr,human resource,training,event,session version : 1.0
homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:cbsession>
release\_dt : 2013-06-12 licenses : Vizsage distribution : Subscription
authorname : JPL TSolucio, S.L. authoremail\_mail :
info(at)tsolucio(dot)com supportemail\_mail : info(at)tsolucio(dot)com
supportissues\_url : \[subscription Contract\] supportsource\_url :
\[subscription URI\]/cbSession.git

------------------------------------------------------------------------

  

Fields
======

### Session Information

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
<td>Session No</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
</tr>
<tr class="even">
<td>Session Name</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>Course</td>
<td>relation</td>
<td>cbTraining</td>
</tr>
<tr class="even">
<td>Date Start</td>
<td>date</td>
<td></td>
</tr>
<tr class="odd">
<td>Time Start</td>
<td>14</td>
<td></td>
</tr>
<tr class="even">
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
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
