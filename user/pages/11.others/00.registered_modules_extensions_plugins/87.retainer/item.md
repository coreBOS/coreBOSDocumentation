---
title: 'Retainer Contract Module'
---

Retainer Contract Module
========================

Contract-like module to register information about condtions of payment
agreed upon for a work to be done.  
This is part of the **Attorney's Back Office** extensions, to control
the retainments.  
---- dataentry ---- name : tsolucio/Retainer type : corebos-module
description\_wiki: Contract-like module to register information about
condtions of payment agreed upon for a work to be done.  
This is part of the **Attorney's Back Office** extensions, to control
the retainments. keywords\_tags :
Contract,retainer,payment,fees,Attorney version : 1.0 homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:retainer>
release\_dt : 2013-06-12 licenses : Vizsage distribution : Subscription
authorname : JPL TSolucio, S.L. authoremail\_mail :
info(at)tsolucio(dot)com supportemail\_mail : info(at)tsolucio(dot)com
supportissues\_url : \[subscription Contract\] supportsource\_url :
\[subscription URI\]/Retainer.git

------------------------------------------------------------------------

  

Fields
======

### Retainer Agreement Information

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
<td>Retainer Agreement Reference</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr class="even">
<td>Retainer Agreement No</td>
<td>autonumber</td>
<td></td>
</tr>
<tr class="odd">
<td>Client</td>
<td>relation</td>
<td>Contacts</td>
</tr>
<tr class="even">
<td>Retainer Agreement Date</td>
<td>date</td>
<td></td>
</tr>
<tr class="odd">
<td>Related to Matter</td>
<td>relation</td>
<td>Project,LitigationMatter</td>
</tr>
</tbody>
</table>

### Hourly Fees and Retainer Deposit Information

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
<td>Attorney Fees 1</td>
<td>number</td>
<td></td>
</tr>
<tr class="even">
<td>Attorney Fees 2</td>
<td>number</td>
<td></td>
</tr>
<tr class="odd">
<td>Paralegal Fees 1</td>
<td>number</td>
<td></td>
</tr>
<tr class="even">
<td>Paralegal Fees 2</td>
<td>number</td>
<td></td>
</tr>
<tr class="odd">
<td>Advanced Retainer Fees 1</td>
<td>number</td>
<td></td>
</tr>
<tr class="even">
<td>Advanced Retainer Fees 2</td>
<td>number</td>
<td></td>
</tr>
<tr class="odd">
<td>Pay Frequency</td>
<td>picklist</td>
<td></td>
</tr>
<tr class="even">
<td>Delinquent After Days</td>
<td>number</td>
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
