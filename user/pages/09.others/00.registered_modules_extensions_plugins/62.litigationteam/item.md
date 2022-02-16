---
title: 'Litigation Team Details'
---

Litigation Team Details
=======================

This module permits defining the details and people working on a
litigation. It is a very basic team management module.  
This is part of the **Attorney's Back Office** extensions.  
---- dataentry ---- name : tsolucio/LitigationTeam type : corebos-module
description\_wiki: This module permits defining the details and people
working on a litigation. It is a very basic team management module.  
This is part of the **Attorney's Back Office** extensions.
keywords\_tags : litigation,users,work,contact,employee,team version :
1.0 homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:litigationteam>
release\_dt : 2013-06-12 licenses : Vizsage price : 250eur
buyemail\_mail : paypal(at)tsolucio(dot)com distribution : Sale
authorname : JPL TSolucio, S.L. authoremail\_mail :
info(at)tsolucio(dot)com supportemail\_mail : info(at)tsolucio(dot)com

------------------------------------------------------------------------

  

Fields
======

### Litigation Team Information

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
<td>Team Name/Description</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr class="even">
<td>Litigation Team No</td>
<td>autonumber</td>
<td></td>
</tr>
<tr class="odd">
<td>Matter Related to</td>
<td>relation</td>
<td>Accounts,Contacts</td>
</tr>
<tr class="even">
<td>Function-Responsibility</td>
<td>relation</td>
<td>LTFunctions</td>
</tr>
<tr class="odd">
<td>Function/Responsibility Execution Priority</td>
<td>picklist</td>
<td>--- Please Select ---,Low,Medium,High,Urgent</td>
</tr>
<tr class="even">
<td>Function/Responsibility Execution Status</td>
<td>picklist</td>
<td>--- Please Select ---,10%,20%,30%,40%,50%,60%,70%,80%,90%,100%</td>
</tr>
<tr class="odd">
<td>Team Leader</td>
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
