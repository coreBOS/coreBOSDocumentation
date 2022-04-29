---
title: 'Bank Accounts'
---

Bank Accounts
=============

Bank Accounts module to register information about the bank accounts you
work with, either your company or your clients accounts.  
This module is related with the Bank module and should be installed
together.  
This is part of the TSolucio **payments extensions** that support **SEPA
and direct bank charges** to your clients.  
---- dataentry ---- name : tsolucio/BankAccounts type : corebos-module
description\_wiki: Bank Accounts module to register information about
the bank accounts you work with, either your company or your clients
accounts.  
This module is related with the Bank module and should be installed
together.  
This is part of the TSolucio **payments extensions** that support **SEPA
and direct bank charges** to your clients.  
keywords\_tags : bank,SEPA,payment version : 1.0 homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:bankaccounts>
release\_dt : 2015-06-12 licenses : Vizsage distribution : Subscription
authorname : JPL TSolucio, S.L. authoremail\_mail :
info(at)tsolucio(dot)com supportemail\_mail : info(at)tsolucio(dot)com
supportissues\_url : \[subscription Contract\] supportsource\_url :
\[subscription URI\]/Bank.git

------------------------------------------------------------------------

  

Fields
======

### Bank Account Information

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
<td>Bank Account Number</td>
<td>1</td>
<td><strong>Identifier</strong></td>
</tr>
<tr class="even">
<td>Account Current Balance</td>
<td>7</td>
<td></td>
</tr>
<tr class="odd">
<td>Account Status</td>
<td>15</td>
<td>--- Please Select ---,Active,Closed</td>
</tr>
<tr class="even">
<td>Bank Account Type</td>
<td>15</td>
<td></td>
</tr>
<tr class="odd">
<td>Related To Client (If Trust Account)</td>
<td>10</td>
<td>Contacts</td>
</tr>
<tr class="even">
<td>Bank Name</td>
<td>10</td>
<td>Bank</td>
</tr>
<tr class="odd">
<td>GL Account</td>
<td>10</td>
<td>GLAccounts</td>
</tr>
<tr class="even">
<td>Account Opening Balance</td>
<td>71</td>
<td></td>
</tr>
<tr class="odd">
<td>Date Account Opened</td>
<td>5</td>
<td></td>
</tr>
<tr class="even">
<td>Date Account Closed</td>
<td>5</td>
<td></td>
</tr>
</tbody>
</table>

### Other Miscellaneous Information

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
<td>Account Service Fees</td>
<td>71</td>
<td></td>
</tr>
<tr class="even">
<td>Account Interest Rate</td>
<td>1</td>
<td></td>
</tr>
<tr class="odd">
<td>Account Overdraft Protection Service Activated</td>
<td>56</td>
<td></td>
</tr>
<tr class="even">
<td>Account Used for Overdraft Protection</td>
<td>10</td>
<td>BankAccounts</td>
</tr>
<tr class="odd">
<td>Debit Card Overdraft Protection Service Activated</td>
<td>56</td>
<td></td>
</tr>
<tr class="even">
<td>Direct Deposit</td>
<td>56</td>
<td></td>
</tr>
<tr class="odd">
<td>Bill Pay Activated</td>
<td>56</td>
<td></td>
</tr>
<tr class="even">
<td>Account Statement Delivery</td>
<td>15</td>
<td>--- Please Select ---,by Mail,On-line,Combined</td>
</tr>
<tr class="odd">
<td>Statement Cycle</td>
<td>1</td>
<td></td>
</tr>
<tr class="even">
<td>Bank Account Nickname</td>
<td>1</td>
<td></td>
</tr>
<tr class="odd">
<td>Authorized Account Signor</td>
<td>1</td>
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
<td>19</td>
<td></td>
</tr>
</tbody>
</table>

### Additional Information

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
<td>Account No</td>
<td>4</td>
<td></td>
</tr>
<tr class="even">
<td>Assigned To</td>
<td>53</td>
<td></td>
</tr>
<tr class="odd">
<td>Created Time</td>
<td>70</td>
<td></td>
</tr>
<tr class="even">
<td>Modified Time</td>
<td>70</td>
<td></td>
</tr>
</tbody>
</table>
