---
title: 'General Ledger Accounts'
---

General Ledger Accounts
=======================

General Ledger Accounts module.  
This is part of the Attorney's BackOffice **accounting extensions**.  
---- dataentry ---- name : tsolucio/GLAccounts type : corebos-module
description\_wiki: General Ledger Accounts module.  
This is part of the Attorney's BackOffice **accounting extensions**.  
keywords\_tags : accounting,ledger version : 1.0 homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:glaccounts>
release\_dt : 2013-03-02 licenses : Vizsage distribution : Subscription
authorname : JPL TSolucio, S.L. authoremail\_mail :
info(at)tsolucio(dot)com supportemail\_mail : info(at)tsolucio(dot)com
supportissues\_url : \[subscription Contract\] supportsource\_url :
\[subscription URI\]/GLAccounts.git

------------------------------------------------------------------------

  

Fields
======

### GL Account Information

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
<td>GL Account Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr class="even">
<td>GL Account Record No</td>
<td>autonumber</td>
<td></td>
</tr>
<tr class="odd">
<td>GL Account Code</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>GL Account Code 2</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>GL Account Group</td>
<td>relation</td>
<td>GLAGroups</td>
</tr>
<tr class="even">
<td>Active GL Account</td>
<td>checkbox</td>
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

### Additional Record Information

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
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
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
