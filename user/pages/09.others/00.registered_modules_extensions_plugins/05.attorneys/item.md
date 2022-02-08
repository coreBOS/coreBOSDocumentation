---
title: 'Attorneys Module'
---

Attorneys Module
================

Contact-like module to register information about the Attorneys in our
office.  
This is part of the **Attorney's Back Office**.  
---- dataentry ---- name : tsolucio/Attorneys type : corebos-module
description\_wiki: Contact-like module to register information about the
Attorneys in our office.  
This is part of the **Attorney's Back Office**. keywords\_tags :
Attorneys,employee version : 1.0 homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:attorneys>
release\_dt : 2013-06-12 licenses : Vizsage price : 250eur
buyemail\_mail : paypal(at)tsolucio(dot)com distribution : Sale
authorname : JPL TSolucio, S.L. authoremail\_mail :
info(at)tsolucio(dot)com supportemail\_mail : info(at)tsolucio(dot)com

------------------------------------------------------------------------

  

Fields
======

### Attorney Information

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
<td>First Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr class="even">
<td>Record No</td>
<td>autonumber</td>
<td></td>
</tr>
<tr class="odd">
<td>Middle Name</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Date Joined the Firm</td>
<td>date</td>
<td></td>
</tr>
<tr class="odd">
<td>Last Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr class="even">
<td>Attorney Supervisor</td>
<td>relation</td>
<td>Attorneys</td>
</tr>
<tr class="odd">
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
</tbody>
</table>

### Home Address

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
<td>City</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>State/Province</td>
<td>picklist</td>
<td></td>
</tr>
<tr class="even">
<td>Zip/Postal Code</td>
<td>string</td>
<td></td>
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
<td>Mobile Phone</td>
<td>11</td>
<td></td>
</tr>
<tr class="odd">
<td>Work Phone</td>
<td>11</td>
<td></td>
</tr>
<tr class="even">
<td>Personal Email</td>
<td>email</td>
<td></td>
</tr>
<tr class="odd">
<td>Work Email</td>
<td>email</td>
<td></td>
</tr>
<tr class="even">
<td>LinkedIn Profile</td>
<td>url</td>
<td></td>
</tr>
<tr class="odd">
<td>Twitter Page</td>
<td>url</td>
<td></td>
</tr>
<tr class="even">
<td>Facebook Page</td>
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

### Legal Practice Areas Specialization

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
<td>Area of Law Specialization</td>
<td>multipicklist</td>
<td></td>
</tr>
</tbody>
</table>

### Compensation and Hourly Rates

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
<td>Yearly Compensation</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Hourly Rate</td>
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
<td>Bar Member Since</td>
<td>date</td>
<td></td>
</tr>
<tr class="even">
<td>County</td>
<td>relation</td>
<td>County</td>
</tr>
<tr class="odd">
<td>Sections</td>
<td>text</td>
<td></td>
</tr>
<tr class="even">
<td>Bar Comments</td>
<td>text</td>
<td></td>
</tr>
</tbody>
</table>

### Education

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
<td>High School</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>High School Graduation Year</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>High School GPA</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>High School Comments</td>
<td>text</td>
<td></td>
</tr>
<tr class="odd">
<td>Undergraduate School</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Undergraduate School Graduation Year</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>Undergraduate School GPA</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Undergraduate School Comments</td>
<td>text</td>
<td></td>
</tr>
<tr class="odd">
<td>Law School</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>LS Graduation Year</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>Law School GPA</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Law School Comments</td>
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
