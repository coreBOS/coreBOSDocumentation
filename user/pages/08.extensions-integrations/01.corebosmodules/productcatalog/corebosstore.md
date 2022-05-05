---
title: 'Product Catalog'
metadata:
    description: 'Product to product relation. Permits establishing a relation between products to indicate things like what date range a product is Required,Standard,Optional,Selectable by another.'
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

Product to product relation. Permits establishing a relation between products to indicate things like what date range a product is Required,Standard,Optional,Selectable by another.

===

### Fields

#### Parent Product Information

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
<td>Related to parent</td>
<td>relation</td>
<td>Products <strong>Identifier</strong></td>
</tr>
<tr>
<td>Parent Catalog</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Parent Code</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Product end sale date</td>
<td>date</td>
<td></td>
</tr>
</tbody>
</table>
<br>
#### Dependent Product Information

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
<td>Related to dependent</td>
<td>relation</td>
<td>Products</td>
</tr>
<tr>
<td>Dependent Catalog</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Dependent Code</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Dependent end sale date</td>
<td>date</td>
<td></td>
</tr>
</tbody>
</table>
<br>
#### Relation Information

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
<td>Relation Mode</td>
<td>picklist</td>
<td>Required,Standard,Optional,Selectable</td>
</tr>
<tr>
<td>Relation from</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Relation Number</td>
<td>autonumber</td>
<td></td>
</tr>
<tr>
<td>Relation to</td>
<td>date</td>
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
</tbody>
</table>
