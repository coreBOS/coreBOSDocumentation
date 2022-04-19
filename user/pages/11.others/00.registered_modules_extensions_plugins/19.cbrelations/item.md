---
title: 'Relationships Module'
---

Relationships Module
====================

Module to register the relation between two accounts, contacts, vendors
or leads.  
The module enables you to record and analyze relationships of a lead, an
account or a contact for a better understanding of its roles,
dependencies and influences.  
---- dataentry ---- name : tsolucio/cbRelations type : corebos-module
description\_wiki: Module to register the relation between two accounts,
contacts, vendors or leads.  
The module enables you to record and analyze relationships of a lead, an
account or a contact for a better understanding of its roles,
dependencies and influences. keywords\_tags :
relation,account,contact,lead,hr,human resources version : 1.0
homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:cbrelations>
release\_dt : 2015-06-27 licenses : Vizsage distribution : Subscription
authorname : JPL TSolucio, S.L. authoremail\_mail :
info(at)tsolucio(dot)com supportemail\_mail : info(at)tsolucio(dot)com
supportissues\_url : \[subscription Contract\] supportsource\_url :
\[subscription URI\]/cbRelations.git

------------------------------------------------------------------------

  

Fields
======

### Relationship Information

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
<td>Actor A</td>
<td>relation</td>
<td>Accounts,Contacts,Vendors,Leads</td>
</tr>
<tr class="even">
<td>Relation Start</td>
<td>date</td>
<td></td>
</tr>
<tr class="odd">
<td>Actor B</td>
<td>relation</td>
<td>Accounts,Contacts,Vendors,Leads</td>
</tr>
<tr class="even">
<td>Relation End</td>
<td>date</td>
<td></td>
</tr>
<tr class="odd">
<td>Relation Type</td>
<td>picklist</td>
<td>Network,Supplier,Family,Work</td>
</tr>
<tr class="even">
<td>Relation No</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
</tr>
<tr class="odd">
<td>Relation Status</td>
<td>picklist</td>
<td>Active,Inactive</td>
</tr>
<tr class="even">
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
<tr class="odd">
<td>Created Time</td>
<td>datetime</td>
<td></td>
</tr>
<tr class="even">
<td>Modified Time</td>
<td>datetime</td>
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
<td>Description</td>
<td>text</td>
<td></td>
</tr>
</tbody>
</table>
