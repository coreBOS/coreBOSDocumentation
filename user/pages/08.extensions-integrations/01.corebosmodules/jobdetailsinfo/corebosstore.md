---
title: 'Job Details Information'
metadata:
    description: 'Job Details Information module.This is part of the Attorneys Back Office Human Resource enhancements.'
    author: 'Joe Bordes'
content:
    items:
        - '@self.children'
    limit: 5
    order:
        by: date
        dir: desc
    pagination: true
    url_taxonomy_filters: true
taxonomy:
    category:
        - extension
    tag:
        - module
---

Job Details Information module.
This is part of the **Attorney's Back Office Human Resource** enhancements.

===

### Fields

#### Job Title, Assigned Supervisor

<table class="table table-striped">
<thead>
<tr class="header">
<th>Field</th>
<th>Type</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr>
<td>Job Title</td>
<td>relation</td>
<td>JobTitle</td>
</tr>
<tr>
<td>Employment Status</td>
<td>picklist</td>
<td>--- Please Select ---,Active,Unactive,Terminated,
Permanent Full-Time,Permanent Part-Time,Temporary Full-Time,
Temporary Part-Time,Contingent. On Call,Contract Full-Time,
Contract Part-Time,Full Time Internship,Part Time Internship,
Hourly Part-Time,Hourly Full-Time</td>
</tr>
<tr>
<td>Date Job Started</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Assigned Supervisor</td>
<td>assigned to</td>
<td></td>
</tr>
</tbody>
</table>
<br>
#### Salary, Other Compensation Details

<table class="table table-striped">
<thead>
<tr class="header">
<th>Field</th>
<th>Type</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr>
<td>Pay Grade</td>
<td>relation</td>
<td>PayGrade</td>
</tr>
<tr>
<td>Pay Frequency</td>
<td>picklist</td>
<td></td>
</tr>
<tr>
<td>Total Compensation Amount (per year)</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Total Compensation Amount per Pay Period</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Total Compensation Amount per Hour</td>
<td>number</td>
<td></td>
</tr>
</tbody>
</table>
<br>
#### Direct Deposit Details

<table class="table table-striped">
<thead>
<tr class="header">
<th>Field</th>
<th>Type</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr>
<td>Bank Account Number</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Bank Account Type</td>
<td>picklist</td>
<td>--- Please Select ---,Business Checking Account,Savings Account,
Personal Checking,Interest-Bearing Checking Account,Money Market Deposit Account,
Trust Account,Certificates of Deposit (CD)</td>
</tr>
<tr>
<td>Bank Account Routing Number</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Deposit Amount</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Deposit comments</td>
<td>text</td>
<td></td>
</tr>
</tbody>
</table>
<br>
#### Tax Exemptions Status

<table class="table table-striped">
<thead>
<tr class="header">
<th>Field</th>
<th>Type</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr>
<td>Federal Filing Status</td>
<td>picklist</td>
<td>--- Please Select ---,Single,Married Filing Jointly,
Married Filing Separately,Head of Household,
Qualifying Widow(er) With Dependent Child</td>
</tr>
<tr>
<td>Number of Federal Allowances</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Additional Federal Withholding</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>State/Province Filing Status</td>
<td>picklist</td>
<td>--- Please Select ---,Single,Married,Widowed,Divorced,
Legally Separated,Civil Union,Domestic Partnership Dissolved,
Registered Domestic Partner,Head of Household,Married Use Single Rate,
Married Filing Separately</td>
</tr>
<tr>
<td>Number of dependents</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Additional State/Province Withholding</td>
<td>number</td>
<td></td>
</tr>
</tbody>
</table>
<br>
#### Custom Information
<br>
#### Description

<table class="table table-striped">
<thead>
<tr class="header">
<th>Field</th>
<th>Type</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr>
<td>Compensation comments</td>
<td>text</td>
<td></td>
</tr>
<tr>
<td>Description</td>
<td>text</td>
<td></td>
</tr>
</tbody>
</table>
<br>
#### Additional Information

<table class="table table-striped">
<thead>
<tr class="header">
<th>Field</th>
<th>Type</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr>
<td>Job Details Reference</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Created Time</td>
<td>datetime</td>
<td></td>
</tr>
<tr>
<td>Modified Time</td>
<td>datetime</td>
<td></td>
</tr>
</tbody>
</table>
