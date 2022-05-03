---
title: 'coreBOS Multi-Address'
metadata:
    description: 'Module to manage many addresses related to Accounts and Contacts. You will be able to relate as many addresses as you need to each account/contact and then establish the default billing and shipping address on them and on each individual Quote, SalesOrder, PurchaseOrder and Invoice.'
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

Module to manage many addresses related to Accounts and Contacts. You will be able to relate as many addresses as you need to each account/contact and then establish the default billing and shipping address on them and on each individual Quote, SalesOrder, PurchaseOrder and Invoice.

===

### Fields

#### Address Information

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
<td>Address Number</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Reference</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Street</td>
<td>text</td>
<td></td>
</tr>
<tr>
<td>PO Box</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>City</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>State</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Postal Code</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Country</td>
<td>string</td>
<td></td>
</tr>
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
