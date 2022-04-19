---
title: 'Litigation Matter Details'
---

Litigation Matter Details
=========================

This project-like module permits defining the details of a litigation
matter our business is working on.  
This is part of the **Attorney's Back Office** extensions.  
---- dataentry ---- name : tsolucio/LitigationMatter type :
corebos-module description\_wiki: This project-like module permits
defining the details of a litigation matter our business is working
on.  
This is part of the **Attorney's Back Office** extensions.
keywords\_tags : litigation,users,work,contact,employee,team,attorney
version : 1.0 homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:litigationmatter>
release\_dt : 2013-06-12 licenses : Vizsage price : 350eur
buyemail\_mail : paypal(at)tsolucio(dot)com distribution : Sale
authorname : JPL TSolucio, S.L. authoremail\_mail :
info(at)tsolucio(dot)com supportemail\_mail : info(at)tsolucio(dot)com

------------------------------------------------------------------------

  

Fields
======

### Parties to the Matter

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
<td>Plaintiff</td>
<td>relation</td>
<td>Accounts,OpposingParty</td>
</tr>
<tr class="even">
<td>Defendant</td>
<td>relation</td>
<td>OpposingParty,Accounts</td>
</tr>
<tr class="odd">
<td>Attorney</td>
<td>relation</td>
<td>Attorneys,OpposingAttorney</td>
</tr>
<tr class="even">
<td>Opposing Attorney</td>
<td>relation</td>
<td>OpposingAttorney,Attorneys</td>
</tr>
</tbody>
</table>

### Litigation Matter Information

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
<td>Matter Name/Caption</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr class="even">
<td>Office Assigned Matter No</td>
<td>autonumber</td>
<td></td>
</tr>
<tr class="odd">
<td>Matter Docket Number</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Matter Filing Date</td>
<td>date</td>
<td></td>
</tr>
<tr class="odd">
<td>Related to Case</td>
<td>relation</td>
<td>Project</td>
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

### Matter Circle

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
<td>Related to Client</td>
<td>relation</td>
<td>Contacts</td>
</tr>
<tr class="even">
<td>Assigned Paralegal</td>
<td>relation</td>
<td>Paralegals</td>
</tr>
<tr class="odd">
<td>Supervising Attorney</td>
<td>relation</td>
<td>Attorneys</td>
</tr>
<tr class="even">
<td>Assigned Secretary</td>
<td>relation</td>
<td>Secretaries</td>
</tr>
<tr class="odd">
<td>Assigned Litigation Team</td>
<td>relation</td>
<td>LitigationTeam</td>
</tr>
<tr class="even">
<td>Matter Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
</tbody>
</table>

### Matter Details and Specifics

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
<td>State</td>
<td>picklist</td>
<td></td>
</tr>
<tr class="even">
<td>Judicial Officer</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>County</td>
<td>relation</td>
<td>County</td>
</tr>
<tr class="even">
<td>Origin of the Matter</td>
<td>picklist</td>
<td>--- Please Select ---,Appeal to District Judge from Magistrate Judgment,Multidistrict Litigation,Original Proceeding,Removed to Federal Court,Removed from State Court,Remanded to State Court,Remanded from Appellate Court,Reinstated or Reopened,Transferred from another District,Non-Litigation Revenue Opportunities</td>
</tr>
<tr class="odd">
<td>Court Name</td>
<td>relation</td>
<td>StateCourt,FederalCourt</td>
</tr>
<tr class="even">
<td>Claim Specifics</td>
<td>picklist</td>
<td></td>
</tr>
<tr class="odd">
<td>Matter Type</td>
<td>picklist</td>
<td></td>
</tr>
<tr class="even">
<td>Claim Amount</td>
<td>number</td>
<td></td>
</tr>
<tr class="odd">
<td>Court Type/Location</td>
<td>picklist</td>
<td></td>
</tr>
<tr class="even">
<td>Nature of Suit</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>State/Federal Court Type</td>
<td>picklist</td>
<td></td>
</tr>
<tr class="even">
<td>Additional Matter Information</td>
<td>text</td>
<td></td>
</tr>
<tr class="odd">
<td>Jurisdiction</td>
<td>picklist</td>
<td></td>
</tr>
<tr class="even">
<td>Jury Requested</td>
<td>checkbox</td>
<td></td>
</tr>
<tr class="odd">
<td>Category</td>
<td>picklist</td>
<td></td>
</tr>
</tbody>
</table>

### Matter Status and Dismissal

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
<td>Matter Status</td>
<td>picklist</td>
<td></td>
</tr>
<tr class="even">
<td>Matter Handling Priority</td>
<td>picklist</td>
<td>--- Please Select ---,Low,Normal,High,Urgent</td>
</tr>
<tr class="odd">
<td>Stage of the Matter</td>
<td>picklist</td>
<td></td>
</tr>
<tr class="even">
<td>Next Appearance Date</td>
<td>date</td>
<td></td>
</tr>
<tr class="odd">
<td>Stage Status</td>
<td>picklist</td>
<td></td>
</tr>
<tr class="even">
<td>Matter Dismissal Date</td>
<td>date</td>
<td></td>
</tr>
<tr class="odd">
<td>Matter Progress</td>
<td>picklist</td>
<td>--- Please Select ---,10%,20%,30%,40%,50%,60%,70%,80%,90%,100%</td>
</tr>
</tbody>
</table>

### Custom Information
