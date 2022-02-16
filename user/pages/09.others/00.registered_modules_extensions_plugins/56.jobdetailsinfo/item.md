---
title: 'Job Details Information'
---

Job Details Information
=======================

Job Details Information module.  
This is part of the **Attorney's Back Office Human Resource**
enhancements.  
---- dataentry ---- name : tsolucio/JobDetailsInfo type : corebos-module
description\_wiki: Job Details Information module.  
This is part of the **Attorney's Back Office Human Resource**
enhancements.  
keywords\_tags : hr,human resource,job,work,position version : 1.0
homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:jobdetailsinfo>
release\_dt : 2013-06-12 licenses : Vizsage distribution : Subscription
authorname : JPL TSolucio, S.L. authoremail\_mail :
info(at)tsolucio(dot)com supportemail\_mail : info(at)tsolucio(dot)com
supportissues\_url : \[subscription Contract\] supportsource\_url :
\[subscription URI\]/JobDetailsInfo.git

------------------------------------------------------------------------

  

Fields
======

### Job Title, Assigned Supervisor

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
<td>Job Title</td>
<td>relation</td>
<td>JobTitle</td>
</tr>
<tr class="even">
<td>Employment Status</td>
<td>picklist</td>
<td>--- Please Select ---,Active,Unactive,Terminated,Permanent Full-Time,Permanent Part-Time,Temporary Full-Time,Temporary Part-Time,Contingent. On Call,Contract Full-Time,Contract Part-Time,Full Time Internship,Part Time Internship,Hourly Part-Time,Hourly Full-Time</td>
</tr>
<tr class="odd">
<td>Date Job Started</td>
<td>date</td>
<td></td>
</tr>
<tr class="even">
<td>Assigned Supervisor</td>
<td>assigned to</td>
<td></td>
</tr>
</tbody>
</table>

### Salary, Other Compensation Details

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
<td>Pay Grade</td>
<td>relation</td>
<td>PayGrade</td>
</tr>
<tr class="even">
<td>Pay Frequency</td>
<td>picklist</td>
<td></td>
</tr>
<tr class="odd">
<td>Total Compensation Amount (per year)</td>
<td>number</td>
<td></td>
</tr>
<tr class="even">
<td>Total Compensation Amount per Pay Period</td>
<td>number</td>
<td></td>
</tr>
<tr class="odd">
<td>Total Compensation Amount per Hour</td>
<td>number</td>
<td></td>
</tr>
</tbody>
</table>

### Direct Deposit Details

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
<td>Bank Account Number</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Bank Account Type</td>
<td>picklist</td>
<td>--- Please Select ---,Business Checking Account,Savings Account,Personal Checking,Interest-Bearing Checking Account,Money Market Deposit Account,Trust Account,Certificates of Deposit (CD)</td>
</tr>
<tr class="odd">
<td>Bank Account Routing Number</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Deposit Amount</td>
<td>number</td>
<td></td>
</tr>
<tr class="odd">
<td>Deposit comments</td>
<td>text</td>
<td></td>
</tr>
</tbody>
</table>

### Tax Exemptions Status

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
<td>Federal Filing Status</td>
<td>picklist</td>
<td>--- Please Select ---,Single,Married Filing Jointly,Married Filing Separately,Head of Household,Qualifying Widow(er) With Dependent Child</td>
</tr>
<tr class="even">
<td>Number of Federal Allowances</td>
<td>number</td>
<td></td>
</tr>
<tr class="odd">
<td>Additional Federal Withholding</td>
<td>number</td>
<td></td>
</tr>
<tr class="even">
<td>State/Province Filing Status</td>
<td>picklist</td>
<td>--- Please Select ---,Single,Married,Widowed,Divorced,Legally Separated,Civil Union,Domestic Partnership Dissolved,Registered Domestic Partner,Head of Household,Married Use Single Rate,Married Filing Separately</td>
</tr>
<tr class="odd">
<td>Number of dependents</td>
<td>number</td>
<td></td>
</tr>
<tr class="even">
<td>Additional State/Province Withholding</td>
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
<td>Compensation comments</td>
<td>text</td>
<td></td>
</tr>
<tr class="even">
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
<td>Job Details Reference</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
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
