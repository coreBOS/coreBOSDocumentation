---
title: 'Ingress and Expense Control module'
---

Ingress and Expense Control module
==================================

An accounting type module to register incoming and outgoing money
charges that happen against different records in the application.  
---- dataentry ---- name : tsolucio/cbControlIngresoGasto type :
corebos-module description\_wiki: An accounting type module to register
incoming and outgoing money charges that happen against different
records in the application. keywords\_tags :
accounting,Ingress,Expense,payment,money,charge,collection version : 1.0
homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:cbcontrolingresogasto>
release\_dt : 2016-29-02 licenses : Vizsage distribution : Subscription
authorname : JPL TSolucio, S.L. authoremail\_mail :
info(at)tsolucio(dot)com supportemail\_mail : info(at)tsolucio(dot)com
supportissues\_url : \[subscription Contract\] supportsource\_url :
\[subscription URI\]/cbControlIngresoGasto.git

------------------------------------------------------------------------

  

Fields
======

### Payment Information:

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
<td>Payment No</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
</tr>
<tr class="odd">
<td>Payment Ref</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Account/Contact</td>
<td>relation</td>
<td>Accounts,Vendors,Contacts,Leads</td>
</tr>
<tr class="odd">
<td>Related entity</td>
<td>relation</td>
<td>Invoice,PurchaseOrder,SalesOrder,Quotes,Campaigns,Potentials,HelpDesk,Project,ProjectMilestone,ProjectTask,Assets,Products,Services,ServiceContracts</td>
</tr>
<tr class="even">
<td>Register Date</td>
<td>date</td>
<td></td>
</tr>
<tr class="odd">
<td>Due Date</td>
<td>date</td>
<td></td>
</tr>
<tr class="even">
<td>Payment Date</td>
<td>date</td>
<td></td>
</tr>
<tr class="odd">
<td>Paid</td>
<td>checkbox</td>
<td></td>
</tr>
<tr class="even">
<td>Credit</td>
<td>checkbox</td>
<td></td>
</tr>
<tr class="odd">
<td>Payment Mode</td>
<td>picklist</td>
<td>Cash,Check,Credit card</td>
</tr>
<tr class="even">
<td>Payment Category</td>
<td>picklist</td>
<td>Infrastructure,Stock,Sale</td>
</tr>
<tr class="odd">
<td>Amount</td>
<td>number</td>
<td></td>
</tr>
<tr class="even">
<td>Cost</td>
<td>number</td>
<td></td>
</tr>
<tr class="odd">
<td>Benefit</td>
<td>string</td>
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
<tr class="even">
<td>Related user</td>
<td>101</td>
<td></td>
</tr>
</tbody>
</table>

### Custom Information

### Description Information:

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
