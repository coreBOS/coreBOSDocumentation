---
title: 'Retainer Contract Module'
metadata:
    description: 'Contract-like module to register information about condtions of payment agreed upon for a work to be done.This is part of the Attorneys Back Office extensions, to control the retainments.'
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

Contract-like module to register information about condtions of payment agreed upon for a work to be done.
This is part of the **Attorney's Back Office** extensions, to control the retainments.

===

### Fields

#### Retainer Agreement Information

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
<td>Retainer Agreement Reference</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Retainer Agreement No</td>
<td>autonumber</td>
<td></td>
</tr>
<tr>
<td>Client</td>
<td>relation</td>
<td>Contacts</td>
</tr>
<tr>
<td>Retainer Agreement Date</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Related to Matter</td>
<td>relation</td>
<td>Project,LitigationMatter</td>
</tr>
</tbody>
</table>
<br>
#### Hourly Fees and Retainer Deposit Information

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
<td>Attorney Fees 1</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Attorney Fees 2</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Paralegal Fees 1</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Paralegal Fees 2</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Advanced Retainer Fees 1</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Advanced Retainer Fees 2</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Pay Frequency</td>
<td>picklist</td>
<td></td>
</tr>
<tr>
<td>Delinquent After Days</td>
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
