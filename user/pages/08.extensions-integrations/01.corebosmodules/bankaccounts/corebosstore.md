---
title: 'Bank Accounts'
metadata:
    description: 'Register information about the bank accounts you work with, either your company or your clients accounts.'
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

### Fields

#### Bank Account Information

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
<td>Bank Account Number</td>
<td>1</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Account Current Balance</td>
<td>7</td>
<td></td>
</tr>
<tr>
<td>Account Status</td>
<td>15</td>
<td>--- Please Select ---,Active,Closed</td>
</tr>
<tr>
<td>Bank Account Type</td>
<td>15</td>
<td></td>
</tr>
<tr>
<td>Related To Client (If Trust Account)</td>
<td>10</td>
<td>Contacts</td>
</tr>
<tr>
<td>Bank Name</td>
<td>10</td>
<td>Bank</td>
</tr>
<tr>
<td>GL Account</td>
<td>10</td>
<td>GLAccounts</td>
</tr>
<tr>
<td>Account Opening Balance</td>
<td>71</td>
<td></td>
</tr>
<tr>
<td>Date Account Opened</td>
<td>5</td>
<td></td>
</tr>
<tr>
<td>Date Account Closed</td>
<td>5</td>
<td></td>
</tr>
</tbody>
</table>

#### Other Miscellaneous Information

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
<td>Account Service Fees</td>
<td>71</td>
<td></td>
</tr>
<tr>
<td>Account Interest Rate</td>
<td>1</td>
<td></td>
</tr>
<tr>
<td>Account Overdraft Protection Service Activated</td>
<td>56</td>
<td></td>
</tr>
<tr>
<td>Account Used for Overdraft Protection</td>
<td>10</td>
<td>BankAccounts</td>
</tr>
<tr>
<td>Debit Card Overdraft Protection Service Activated</td>
<td>56</td>
<td></td>
</tr>
<tr>
<td>Direct Deposit</td>
<td>56</td>
<td></td>
</tr>
<tr>
<td>Bill Pay Activated</td>
<td>56</td>
<td></td>
</tr>
<tr>
<td>Account Statement Delivery</td>
<td>15</td>
<td>--- Please Select ---,by Mail,On-line,Combined</td>
</tr>
<tr>
<td>Statement Cycle</td>
<td>1</td>
<td></td>
</tr>
<tr>
<td>Bank Account Nickname</td>
<td>1</td>
<td></td>
</tr>
<tr>
<td>Authorized Account Signor</td>
<td>1</td>
<td></td>
</tr>
</tbody>
</table>

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
<td>19</td>
<td></td>
</tr>
</tbody>
</table>

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
<td>Account No</td>
<td>4</td>
<td></td>
</tr>
<tr>
<td>Assigned To</td>
<td>53</td>
<td></td>
</tr>
<tr>
<td>Created Time</td>
<td>70</td>
<td></td>
</tr>
<tr>
<td>Modified Time</td>
<td>70</td>
<td></td>
</tr>
</tbody>
</table>
