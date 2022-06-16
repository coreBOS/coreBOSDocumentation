---
title: 'Opposing Attorneys Module'
metadata:
    description: 'Contact-like module to register information about the Opposing Attorneys we face in litigation matters.This is part of the Attorneys Back Office.'
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
---
Contact-like module to register information about the Opposing Attorneys we face in litigation matters.
This is part of the **Attorney's Back Office**.

===

### Fields

#### Opposing Attorney Information

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
<td>Attorney First Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Opposing Attorney No</td>
<td>autonumber</td>
<td></td>
</tr>
<tr>
<td>Middle Name</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Law Firm-Company Name</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Attorney Last Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Attorney Legal Practice Area</td>
<td>picklist</td>
<td></td>
</tr>
<tr>
<td>Role</td>
<td>picklist</td>
<td>--- Please Select ---,Attorney,Department Manager,Case Manager,Account Representative,Home Preservation Specialist,Customer Case Representative,Customer Support Specialist,Clerk,Trustee</td>
</tr>
</tbody>
</table>
<br>
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
<td>Primary Phone</td>
<td>11</td>
<td></td>
</tr>
<tr>
<td>Email</td>
<td>email</td>
<td></td>
</tr>
<tr>
<td>Mobile Phone</td>
<td>11</td>
<td></td>
</tr>
<tr>
<td>Alternate Email</td>
<td>email</td>
<td></td>
</tr>
<tr>
<td>Alternate Phone</td>
<td>11</td>
<td></td>
</tr>
<tr>
<td>LinkedIn Profile</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Fax</td>
<td>11</td>
<td></td>
</tr>
<tr>
<td>Facebook Page</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Website</td>
<td>url</td>
<td></td>
</tr>
<tr>
<td>Twitter Page</td>
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
<br>
#### Address Information

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
<td>Alternate Address</td>
<td>text</td>
<td></td>
</tr>
<tr>
<td>City</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Alternate City</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>State/Province</td>
<td>picklist</td>
<td></td>
</tr>
<tr>
<td>Alternate State/Province</td>
<td>picklist</td>
<td></td>
</tr>
<tr>
<td>ZIP-Postal Code</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Alternate ZIP-Postal Code</td>
<td>string</td>
<td></td>
</tr>
</tbody>
</table>
<br>
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
<td>Bar County</td>
<td>relation</td>
<td>County</td>
</tr>
<tr>
<td>Bar Member Status - Active</td>
<td>checkbox</td>
<td></td>
</tr>
<tr>
<td>Undergraduate School</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Bar Member Since</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Law School</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Disciplinary, Administrative or Related Actions</td>
<td>text</td>
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
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
<tr>
<td>Notify Owner</td>
<td>checkbox</td>
<td></td>
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
