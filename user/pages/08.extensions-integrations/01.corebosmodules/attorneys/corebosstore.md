---
title: 'Attorneys'
metadata:
    description: 'Contact-like module to register information about the Attorneys in our office.'
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

### Fields

#### Attorney Information

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
<td>First Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Record No</td>
<td>autonumber</td>
<td></td>
</tr>
<tr>
<td>Middle Name</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Date Joined the Firm</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Last Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Attorney Supervisor</td>
<td>relation</td>
<td>Attorneys</td>
</tr>
<tr>
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
</tbody>
</table>

#### Home Address

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
<td>Address</td>
<td>text</td>
<td></td>
</tr>
<tr>
<td>City</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>State/Province</td>
<td>picklist</td>
<td></td>
</tr>
<tr>
<td>Zip/Postal Code</td>
<td>string</td>
<td></td>
</tr>
</tbody>
</table>

#### Phones, E-mails, Website, Social Network Information

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
<td>Home Phone</td>
<td>11</td>
<td></td>
</tr>
<tr>
<td>Mobile Phone</td>
<td>11</td>
<td></td>
</tr>
<tr>
<td>Work Phone</td>
<td>11</td>
<td></td>
</tr>
<tr>
<td>Personal Email</td>
<td>email</td>
<td></td>
</tr>
<tr>
<td>Work Email</td>
<td>email</td>
<td></td>
</tr>
<tr>
<td>LinkedIn Profile</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Twitter Page</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Facebook Page</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Skype ID</td>
<td>85</td>
<td></td>
</tr>
<tr>
<td>GTalk ID</td>
<td>string</td>
<td></td>
</tr>
</tbody>
</table>

#### Legal Practice Areas Specialization

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
<td>Area of Law Specialization</td>
<td>multipicklist</td>
<td></td>
</tr>
</tbody>
</table>

#### Compensation and Hourly Rates

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
<td>Yearly Compensation</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Hourly Rate</td>
<td>string</td>
<td></td>
</tr>
</tbody>
</table>

#### Bar Association Information

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
<td>Bar Member of the State of</td>
<td>picklist</td>
<td></td>
</tr>
<tr>
<td>Bar Number</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Bar Member Since</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>County</td>
<td>relation</td>
<td>County</td>
</tr>
<tr>
<td>Sections</td>
<td>text</td>
<td></td>
</tr>
<tr>
<td>Bar Comments</td>
<td>text</td>
<td></td>
</tr>
</tbody>
</table>

#### Education

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
<td>High School</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>High School Graduation Year</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>High School GPA</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>High School Comments</td>
<td>text</td>
<td></td>
</tr>
<tr>
<td>Undergraduate School</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Undergraduate School Graduation Year</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Undergraduate School GPA</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Undergraduate School Comments</td>
<td>text</td>
<td></td>
</tr>
<tr>
<td>Law School</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>LS Graduation Year</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Law School GPA</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Law School Comments</td>
<td>text</td>
<td></td>
</tr>
</tbody>
</table>

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
<td>Description</td>
<td>text</td>
<td></td>
</tr>
</tbody>
</table>

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
