---
title: 'Job Title Information'
metadata:
    description: 'Job Title Information module.This is part of the Attorneys Back Office Human Resource enhancements.'
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
Job Title Information module.
This is part of the **Attorney's Back Office Human Resource** enhancements.

===

### Fields

#### Job Title Information

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
<td>Job Title Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Job Title Record No</td>
<td>autonumber</td>
<td></td>
</tr>
<tr>
<td>Pay Grade</td>
<td>relation</td>
<td>PayGrade</td>
</tr>
<tr>
<td>Employment Status</td>
<td>picklist</td>
<td></td>
</tr>
<tr>
<td>Department</td>
<td>picklist</td>
<td>--- Please Select ---,Litigation Department,Litigation Support Department,
Transactional Department,HR Department,Marketing Department,Sales Department,
Customer Support Department,IT Department,General Services Department,Other</td>
</tr>
<tr>
<td>Reports to</td>
<td>101</td>
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
<td>Job Description</td>
<td>text</td>
<td></td>
</tr>
<tr>
<td>Job-related Responsibilities</td>
<td>text</td>
<td></td>
</tr>
<tr>
<td>Comments</td>
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
