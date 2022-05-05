---
title: 'Juror'
metadata:
    description: 'Contact like module to register information about jurors.This is part of the Attorneys Back Office application.'
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

Contact like module to register information about jurors.
This is part of the **Attorneys Back Office** application.

===

### Fields

#### Juror Information

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
<td>Juror First Name</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Juror Record No</td>
<td>autonumber</td>
<td></td>
</tr>
<tr>
<td>Juror Last Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Juror Date of Birth</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Juror Occupation</td>
<td>relation</td>
<td>Occupation</td>
</tr>
<tr>
<td>Work Place - Company Name</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Industry Sector</td>
<td>picklist</td>
<td></td>
</tr>
<tr>
<td>Requires Special Accommodation</td>
<td>checkbox</td>
<td></td>
</tr>
<tr>
<td>No of Years Employed by the same Company</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Gender</td>
<td>picklist</td>
<td>--- Please Select ---,Male,Female</td>
</tr>
<tr>
<td>Marital Status</td>
<td>picklist</td>
<td></td>
</tr>
<tr>
<td>Race-Ethnic Group</td>
<td>picklist</td>
<td>--- Please Select ---,White,Black or African American,American Indian or Alaska Native,Asian Indian,Chinese,Filipino,Japanese,Korean,Vietnamese,Other Asian,Central American or South American,Cuban,Dominican,Mexican, Mexican American, Chicano,Other Hispanic or Latino,Puerto Rican,Native Hawaiian,Guamian or Chamorro,Samoan,Other Pacific Islander,Islander,Other</td>
</tr>
<tr>
<td>Smoker</td>
<td>checkbox</td>
<td></td>
</tr>
<tr>
<td>Military Service</td>
<td>checkbox</td>
<td></td>
</tr>
<tr>
<td>Has Children?</td>
<td>checkbox</td>
<td></td>
</tr>
<tr>
<td>Number of Children-Dependent</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Prior Occupation-Profession</td>
<td>relation</td>
<td>Occupation</td>
</tr>
<tr>
<td>Retired?</td>
<td>checkbox</td>
<td></td>
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
<td>Fax</td>
<td>11</td>
<td></td>
</tr>
<tr>
<td>LinkedIn Profile</td>
<td>url</td>
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
