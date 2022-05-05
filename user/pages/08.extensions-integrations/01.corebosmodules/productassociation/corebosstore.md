---
title: 'Product Association'
metadata:
    description: 'Product to product relation. Permits establishing a relation between products to indicate things like what date range a product is Required,Incompatible,Optional,Marketing,Obsolete,Substitute by another.'
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

Product to product relation. Permits establishing a relation between products to indicate things like what date range a product is Required,Incompatible,Optional,Marketing,Obsolete,Substitute by another.

===

### Fields

#### Product Association Information

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
<td>From Product</td>
<td>relation</td>
<td>Products</td>
</tr>
<tr>
<td>To Product</td>
<td>relation</td>
<td>Products</td>
</tr>
<tr>
<td>Relation Mode</td>
<td>picklist</td>
<td>Required,Marketing,Substitue,Complement,
Incompatible,Obsolesence</td>
</tr>
<tr>
<td>Valid from</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Relation Number</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Valid to</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Quantity</td>
<td>number</td>
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
<tr>
<td>Instructions</td>
<td>text</td>
<td></td>
</tr>
</tbody>
</table>
