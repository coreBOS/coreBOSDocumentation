---
title: 'Opposing Party Module'
metadata:
    description: 'Contact-like module to register information about the Opposing Party we face in litigation matters.This is part of the Attorneys Back Office.'
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
Contact-like module to register information about the Opposing Party we face in litigation matters.
This is part of the **Attorney's Back Office**.

===

### Fields

#### Opposing Party Information

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
<td>Party First Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Opposing Party No</td>
<td>autonumber</td>
<td></td>
</tr>
<tr>
<td>Party Last Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Company Name</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Party Type</td>
<td>picklist</td>
<td></td>
</tr>
<tr>
<td>Occupation</td>
<td>relation</td>
<td>Occupation</td>
</tr>
<tr>
<td>Party Designation</td>
<td>picklist</td>
<td>--- Please Select ---,Plaintiff,Defendant,Appellant,Appellee,Respondent,Intervenor,Third-Party Plantiff,Third-Party Defendant</td>
</tr>
<tr>
<td>Industry Sector</td>
<td>picklist</td>
<td></td>
</tr>
<tr>
<td>Related to Matter</td>
<td>relation</td>
<td>Project,LitigationMatter</td>
</tr>
<tr>
<td>Opposing Attorney Name</td>
<td>relation</td>
<td>OpposingAttorney</td>
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
<td>Home Phone</td>
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
<td>Other Phone</td>
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
#### Opposing Party Address

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
<td>Zip/Postal Code</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Alternate Zip/Postal Code</td>
<td>string</td>
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
