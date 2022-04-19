---
title: 'Product Association'
---

Product Association
===================

Product to product relation. Permits establishing a relation between
products to indicate things like what date range a product is
Required,Incompatible,Optional,Marketing,Obsolete,Substitute by
another.  
---- dataentry ---- name : tsolucio/ProductAssociation type :
corebos-module description\_wiki: Product to product relation. Permits
establishing a relation between products to indicate things like what
date range a product is
Required,Incompatible,Optional,Marketing,Obsolete,Substitute by another.
keywords\_tags :
product,relation,category,association,dependency,obsolete version : 1.0
homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:productassociation>
release\_dt : 2016-05-19 licenses : Vizsage distribution : Subscription
authorname : JPL TSolucio, S.L. authoremail\_mail :
info(at)tsolucio(dot)com supportemail\_mail : info(at)tsolucio(dot)com
supportissues\_url : \[subscription Contract\] supportsource\_url :
\[subscription URI\]/ProductAssociation.git

------------------------------------------------------------------------

  

Fields
======

### Product Association Information

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
<td>From Product</td>
<td>relation</td>
<td>Products</td>
</tr>
<tr class="even">
<td>To Product</td>
<td>relation</td>
<td>Products</td>
</tr>
<tr class="odd">
<td>Relation Mode</td>
<td>picklist</td>
<td>Required,Marketing,Substitue,Complement,Incompatible,Obsolesence</td>
</tr>
<tr class="even">
<td>Valid from</td>
<td>date</td>
<td></td>
</tr>
<tr class="odd">
<td>Relation Number</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
</tr>
<tr class="even">
<td>Valid to</td>
<td>date</td>
<td></td>
</tr>
<tr class="odd">
<td>Quantity</td>
<td>number</td>
<td></td>
</tr>
<tr class="even">
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
<tr class="odd">
<td>Created Time</td>
<td>datetime</td>
<td></td>
</tr>
<tr class="even">
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
<tr class="even">
<td>Instructions</td>
<td>text</td>
<td></td>
</tr>
</tbody>
</table>
