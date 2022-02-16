---
title: 'Opposing Party Module'
---

Opposing Party Module
=====================

Contact-like module to register information about the Opposing Party we
face in litigation matters.  
This is part of the **Attorney's Back Office**.  
---- dataentry ---- name : tsolucio/OpposingParty type : corebos-module
description\_wiki: Contact-like module to register information about the
Opposing Party we face in litigation matters.  
This is part of the **Attorney's Back Office**. keywords\_tags :
Attorneys,employee version : 1.0 homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:opposingparty>
release\_dt : 2013-06-12 licenses : Vizsage price : 250eur
buyemail\_mail : paypal(at)tsolucio(dot)com distribution : Sale
authorname : JPL TSolucio, S.L. authoremail\_mail :
info(at)tsolucio(dot)com supportemail\_mail : info(at)tsolucio(dot)com

------------------------------------------------------------------------

  

Fields
======

### Opposing Party Information

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
<td>Party First Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr class="even">
<td>Opposing Party No</td>
<td>autonumber</td>
<td></td>
</tr>
<tr class="odd">
<td>Party Last Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr class="even">
<td>Company Name</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>Party Type</td>
<td>picklist</td>
<td></td>
</tr>
<tr class="even">
<td>Occupation</td>
<td>relation</td>
<td>Occupation</td>
</tr>
<tr class="odd">
<td>Party Designation</td>
<td>picklist</td>
<td>--- Please Select ---,Plaintiff,Defendant,Appellant,Appellee,Respondent,Intervenor,Third-Party Plantiff,Third-Party Defendant</td>
</tr>
<tr class="even">
<td>Industry Sector</td>
<td>picklist</td>
<td></td>
</tr>
<tr class="odd">
<td>Related to Matter</td>
<td>relation</td>
<td>Project,LitigationMatter</td>
</tr>
<tr class="even">
<td>Opposing Attorney Name</td>
<td>relation</td>
<td>OpposingAttorney</td>
</tr>
</tbody>
</table>

### Phones, E-mails, Website, Social Network Information

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
<td>Home Phone</td>
<td>11</td>
<td></td>
</tr>
<tr class="even">
<td>Email</td>
<td>email</td>
<td></td>
</tr>
<tr class="odd">
<td>Mobile Phone</td>
<td>11</td>
<td></td>
</tr>
<tr class="even">
<td>Alternate Email</td>
<td>email</td>
<td></td>
</tr>
<tr class="odd">
<td>Other Phone</td>
<td>11</td>
<td></td>
</tr>
<tr class="even">
<td>LinkedIn Profile</td>
<td>url</td>
<td></td>
</tr>
<tr class="odd">
<td>Fax</td>
<td>11</td>
<td></td>
</tr>
<tr class="even">
<td>Facebook Page</td>
<td>url</td>
<td></td>
</tr>
<tr class="odd">
<td>Website</td>
<td>url</td>
<td></td>
</tr>
<tr class="even">
<td>Twitter Page</td>
<td>url</td>
<td></td>
</tr>
<tr class="odd">
<td>Skype ID</td>
<td>85</td>
<td></td>
</tr>
<tr class="even">
<td>GTalk ID</td>
<td>string</td>
<td></td>
</tr>
</tbody>
</table>

### Opposing Party Address

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
<td>Address</td>
<td>text</td>
<td></td>
</tr>
<tr class="even">
<td>Alternate Address</td>
<td>text</td>
<td></td>
</tr>
<tr class="odd">
<td>City</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Alternate City</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>State/Province</td>
<td>picklist</td>
<td></td>
</tr>
<tr class="even">
<td>Alternate State/Province</td>
<td>picklist</td>
<td></td>
</tr>
<tr class="odd">
<td>Zip/Postal Code</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Alternate Zip/Postal Code</td>
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
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
<tr class="even">
<td>Notify Owner</td>
<td>checkbox</td>
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
