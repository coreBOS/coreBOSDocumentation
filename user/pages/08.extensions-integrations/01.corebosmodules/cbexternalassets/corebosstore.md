---
title: 'External Assets module'
metadata:
    description: 'An asset type module (really an asset clone) to register equipment and machines present in our clients installations that were not sold by us but that we are interested in controling/substituting.'
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

An asset type module (really an asset clone) to register equipment and machines present in our clients installations that were not sold by us but that we are interested in controling/substituting.

===

### Fields

#### External Asset Information

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
<td>External Asset No</td>
<td>autonumber</td>
<td></td>
</tr>
<tr>
<td>Product Name</td>
<td>relation</td>
<td>Products</td>
</tr>
<tr>
<td>Serial Number</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Date Sold</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Date in Service</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Status</td>
<td>picklist</td>
<td>In Service,Out-of-service</td>
</tr>
<tr>
<td>Tag Number</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Shipping Method</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Shipping Tracking Number</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
<tr>
<td>External Asset Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Customer Name</td>
<td>relation</td>
<td>Accounts</td>
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
<td>Last Modified By</td>
<td>52</td>
<td></td>
</tr>
</tbody>
</table>
<br>
#### Custom Information
<br>
#### Notes

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
<td>Notes</td>
<td>text</td>
<td></td>
</tr>
</tbody>
</table>
