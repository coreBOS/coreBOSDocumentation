---
title: 'Litigation Matter Details'
metadata:
    description: 'This project-like module permits defining the details of a litigation matter our business is working on.This is part of the Attorneys Back Office extensions.'
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
This project-like module permits defining the details of a litigation matter our business is working on.
This is part of the **Attorney's Back Office** extensions.

===

### Fields

#### Parties to the Matter

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
<td>Plaintiff</td>
<td>relation</td>
<td>Accounts,OpposingParty</td>
</tr>
<tr>
<td>Defendant</td>
<td>relation</td>
<td>OpposingParty,Accounts</td>
</tr>
<tr>
<td>Attorney</td>
<td>relation</td>
<td>Attorneys,OpposingAttorney</td>
</tr>
<tr>
<td>Opposing Attorney</td>
<td>relation</td>
<td>OpposingAttorney,Attorneys</td>
</tr>
</tbody>
</table>
<br>
#### Litigation Matter Information

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
<td>Matter Name/Caption</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Office Assigned Matter No</td>
<td>autonumber</td>
<td></td>
</tr>
<tr>
<td>Matter Docket Number</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Matter Filing Date</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Related to Case</td>
<td>relation</td>
<td>Project</td>
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
<br>
#### Matter Circle

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
<td>Related to Client</td>
<td>relation</td>
<td>Contacts</td>
</tr>
<tr>
<td>Assigned Paralegal</td>
<td>relation</td>
<td>Paralegals</td>
</tr>
<tr>
<td>Supervising Attorney</td>
<td>relation</td>
<td>Attorneys</td>
</tr>
<tr>
<td>Assigned Secretary</td>
<td>relation</td>
<td>Secretaries</td>
</tr>
<tr>
<td>Assigned Litigation Team</td>
<td>relation</td>
<td>LitigationTeam</td>
</tr>
<tr>
<td>Matter Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
</tbody>
</table>
<br>
#### Matter Details and Specifics

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
<td>State</td>
<td>picklist</td>
<td></td>
</tr>
<tr>
<td>Judicial Officer</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>County</td>
<td>relation</td>
<td>County</td>
</tr>
<tr>
<td>Origin of the Matter</td>
<td>picklist</td>
<td>--- Please Select ---,Appeal to District Judge from Magistrate Judgment,
Multidistrict Litigation,Original Proceeding,Removed to Federal Court,
Removed from State Court,Remanded to State Court,
Remanded from Appellate Court,Reinstated or Reopened,
Transferred from another District,Non-Litigation Revenue Opportunities</td>
</tr>
<tr>
<td>Court Name</td>
<td>relation</td>
<td>StateCourt,FederalCourt</td>
</tr>
<tr>
<td>Claim Specifics</td>
<td>picklist</td>
<td></td>
</tr>
<tr>
<td>Matter Type</td>
<td>picklist</td>
<td></td>
</tr>
<tr>
<td>Claim Amount</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Court Type/Location</td>
<td>picklist</td>
<td></td>
</tr>
<tr>
<td>Nature of Suit</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>State/Federal Court Type</td>
<td>picklist</td>
<td></td>
</tr>
<tr>
<td>Additional Matter Information</td>
<td>text</td>
<td></td>
</tr>
<tr>
<td>Jurisdiction</td>
<td>picklist</td>
<td></td>
</tr>
<tr>
<td>Jury Requested</td>
<td>checkbox</td>
<td></td>
</tr>
<tr>
<td>Category</td>
<td>picklist</td>
<td></td>
</tr>
</tbody>
</table>
<br>
#### Matter Status and Dismissal

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
<td>Matter Status</td>
<td>picklist</td>
<td></td>
</tr>
<tr>
<td>Matter Handling Priority</td>
<td>picklist</td>
<td>--- Please Select ---,Low,Normal,High,Urgent</td>
</tr>
<tr>
<td>Stage of the Matter</td>
<td>picklist</td>
<td></td>
</tr>
<tr>
<td>Next Appearance Date</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Stage Status</td>
<td>picklist</td>
<td></td>
</tr>
<tr>
<td>Matter Dismissal Date</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Matter Progress</td>
<td>picklist</td>
<td>--- Please Select ---,10%,20%,30%,40%,50%,60%,70%,80%,90%,100%</td>
</tr>
</tbody>
</table>
<br>
#### Custom Information
