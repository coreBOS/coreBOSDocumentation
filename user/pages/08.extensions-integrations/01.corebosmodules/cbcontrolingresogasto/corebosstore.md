---
title: 'Ingress and Expense Control module'
metadata:
    description: 'An accounting type module to register incoming and outgoing money charges that happen against different records in the application.'
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
        - payments
        - ingress
---
---
An accounting type module to register incoming and outgoing money charges that happen against different records in the application.

===

### Fields

#### Payment Information

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
<td>Payment No</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Payment Ref</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Account/Contact</td>
<td>relation</td>
<td>Accounts,Vendors,Contacts,Leads</td>
</tr>
<tr>
<td>Related entity</td>
<td>relation</td>
<td>Invoice,PurchaseOrder,SalesOrder,Quotes,Campaigns,
Potentials,HelpDesk,Project,ProjectMilestone,ProjectTask,
Assets,Products,Services,ServiceContracts
</td>
</tr>
<tr>
<td>Register Date</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Due Date</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Payment Date</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Paid</td>
<td>checkbox</td>
<td></td>
</tr>
<tr>
<td>Credit</td>
<td>checkbox</td>
<td></td>
</tr>
<tr>
<td>Payment Mode</td>
<td>picklist</td>
<td>Cash,Check,Credit card</td>
</tr>
<tr>
<td>Payment Category</td>
<td>picklist</td>
<td>Infrastructure,Stock,Sale</td>
</tr>
<tr>
<td>Amount</td>
<td>number</td>
<td></td>
</tr>

<tr>
<td>Cost</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Benefit</td>
<td>string</td>
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
<tr>
<td>Related user</td>
<td>101</td>
<td></td>
</tr>
</tbody>
</table>
<br>
#### Custom Information
<br>
#### Description Information:

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
