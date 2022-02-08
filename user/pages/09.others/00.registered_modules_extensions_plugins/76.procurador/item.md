---
title: 'Procurator module'
---

Procurator module
=================

Contact-like module to register information about procurators that work
with our business.  
This is part of the **Attorney's Back Office** **Human Resources**
extensions.  
---- dataentry ---- name : tsolucio/Procurador type : corebos-module
description\_wiki: Contact-like module to register information about
procurators that work with our business.  
This is part of the **Attorney's Back Office** **Human Resources**
extensions. keywords\_tags : HR,human
resource,procurador,procurator,contact,employee version : 1.0
homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:procurador>
release\_dt : 2013-06-12 licenses : Vizsage distribution : Subscription
authorname : JPL TSolucio, S.L. authoremail\_mail :
info(at)tsolucio(dot)com supportemail\_mail : info(at)tsolucio(dot)com
supportissues\_url : \[subscription Contract\] supportsource\_url :
\[subscription URI\]/Procurador.git

------------------------------------------------------------------------

  

Fields
======

### Solicitor Information

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
<td>NIF/CIF</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Solicitor No</td>
<td>autonumber</td>
<td></td>
</tr>
<tr class="odd">
<td>Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr class="even">
<td>Date Joined the Firm</td>
<td>date</td>
<td></td>
</tr>
<tr class="odd">
<td>Collegiate Number</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Job Title</td>
<td>relation</td>
<td>JobTitle</td>
</tr>
<tr class="odd">
<td>Company Department</td>
<td>picklist</td>
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
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Apt./Suite</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>City</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>State/Province</td>
<td>picklist</td>
<td></td>
</tr>
<tr class="odd">
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
<td>Comments</td>
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
<td>Comments</td>
<td>text</td>
<td></td>
</tr>
<tr class="odd">
<td>Postgraduate Degree/School</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Postgraduate School Graduation Year</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>Postgraduate Degree-School GPA</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Comments</td>
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
