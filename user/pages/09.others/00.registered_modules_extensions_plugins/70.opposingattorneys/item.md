---
title: 'Opposing Attorneys Module'
---

Opposing Attorneys Module
=========================

Contact-like module to register information about the Opposing Attorneys
we face in litigation matters.  
This is part of the **Attorney's Back Office**.  
---- dataentry ---- name : tsolucio/OpposingAttorney type :
corebos-module description\_wiki: Contact-like module to register
information about the Opposing Attorneys we face in litigation
matters.  
This is part of the **Attorney's Back Office**. keywords\_tags :
Attorneys,employee version : 1.0 homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:opposingattorneys>
release\_dt : 2013-06-12 licenses : Vizsage price : 250eur
buyemail\_mail : paypal(at)tsolucio(dot)com distribution : Sale
authorname : JPL TSolucio, S.L. authoremail\_mail :
info(at)tsolucio(dot)com supportemail\_mail : info(at)tsolucio(dot)com

------------------------------------------------------------------------

  

Fields
======

### Opposing Attorney Information

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
<td>Attorney First Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr class="even">
<td>Opposing Attorney No</td>
<td>autonumber</td>
<td></td>
</tr>
<tr class="odd">
<td>Middle Name</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Law Firm-Company Name</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>Attorney Last Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr class="even">
<td>Attorney Legal Practice Area</td>
<td>picklist</td>
<td></td>
</tr>
<tr class="odd">
<td>Role</td>
<td>picklist</td>
<td>--- Please Select ---,Attorney,Department Manager,Case Manager,Account Representative,Home Preservation Specialist,Customer Case Representative,Customer Support Specialist,Clerk,Trustee</td>
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
<td>Primary Phone</td>
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
<td>Alternate Phone</td>
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

### Address Information

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
<td>ZIP-Postal Code</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Alternate ZIP-Postal Code</td>
<td>string</td>
<td></td>
</tr>
</tbody>
</table>

### Bar Association Information

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
<td>Bar Member of the State of</td>
<td>picklist</td>
<td></td>
</tr>
<tr class="even">
<td>Bar Number</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>Bar County</td>
<td>relation</td>
<td>County</td>
</tr>
<tr class="even">
<td>Bar Member Status - Active</td>
<td>checkbox</td>
<td></td>
</tr>
<tr class="odd">
<td>Undergraduate School</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Bar Member Since</td>
<td>date</td>
<td></td>
</tr>
<tr class="odd">
<td>Law School</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Disciplinary, Administrative or Related Actions</td>
<td>text</td>
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
