---
title: 'Product Catalog'
---

Product Catalog
===============

Product to product relation. Permits establishing a relation between
products to indicate things like what date range a product is
Required,Standard,Optional,Selectable by another.  
---- dataentry ---- name : tsolucio/ProductCatalog type : corebos-module
description\_wiki: Product to product relation. Permits establishing a
relation between products to indicate things like what date range a
product is Required,Standard,Optional,Selectable by another.
keywords\_tags : product,relation,category,dependency version : 1.0
homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:productcatalog>
release\_dt : 2014-12-24 licenses : Vizsage distribution : Subscription
authorname : JPL TSolucio, S.L. authoremail\_mail :
info(at)tsolucio(dot)com supportemail\_mail : info(at)tsolucio(dot)com
supportissues\_url : \[subscription Contract\] supportsource\_url :
\[subscription URI\]/ProductCatalog.git

------------------------------------------------------------------------

  

Fields
======

### Parent Product Information

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
<td>Related to parent</td>
<td>relation</td>
<td>Products <strong>Identifier</strong></td>
</tr>
<tr class="even">
<td>Parent Catalog</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>Parent Code</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Product end sale date</td>
<td>date</td>
<td></td>
</tr>
</tbody>
</table>

### Dependent Product Information

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
<td>Related to dependent</td>
<td>relation</td>
<td>Products</td>
</tr>
<tr class="even">
<td>Dependent Catalog</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>Dependent Code</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Dependent end sale date</td>
<td>date</td>
<td></td>
</tr>
</tbody>
</table>

### Relation Information

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
<td>Relation Mode</td>
<td>picklist</td>
<td>Required,Standard,Optional,Selectable</td>
</tr>
<tr class="even">
<td>Relation from</td>
<td>date</td>
<td></td>
</tr>
<tr class="odd">
<td>Relation Number</td>
<td>autonumber</td>
<td></td>
</tr>
<tr class="even">
<td>Relation to</td>
<td>date</td>
<td></td>
</tr>
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
