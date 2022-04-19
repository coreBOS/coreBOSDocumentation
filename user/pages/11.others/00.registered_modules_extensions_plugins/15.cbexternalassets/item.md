---
title: 'External Assets module'
---

External Assets module
======================

An asset type module (really an asset clone) to register equipment and
machines present in our clients installations that were not sold by us
but that we are interested in controling/substituting.  
---- dataentry ---- name : tsolucio/cbExternalAssets type :
corebos-module description\_wiki: An asset type module (really an asset
clone) to register equipment and machines present in our clients
installations that were not sold by us but that we are interested in
controling/substituting. keywords\_tags :
asset,equipment,terminal,machine,inventory,competition,vendor version :
1.0 homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:cbexternalassets>
release\_dt : 2016-03-14 licenses : Vizsage distribution : Subscription
authorname : JPL TSolucio, S.L. authoremail\_mail :
info(at)tsolucio(dot)com supportemail\_mail : info(at)tsolucio(dot)com
supportissues\_url : \[subscription Contract\] supportsource\_url :
\[subscription URI\]/cbExternalAssets.git

------------------------------------------------------------------------

  

Fields
======

### External Asset Information

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
<td>External Asset No</td>
<td>autonumber</td>
<td></td>
</tr>
<tr class="even">
<td>Product Name</td>
<td>relation</td>
<td>Products</td>
</tr>
<tr class="odd">
<td>Serial Number</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Date Sold</td>
<td>date</td>
<td></td>
</tr>
<tr class="odd">
<td>Date in Service</td>
<td>date</td>
<td></td>
</tr>
<tr class="even">
<td>Status</td>
<td>picklist</td>
<td>In Service,Out-of-service</td>
</tr>
<tr class="odd">
<td>Tag Number</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Shipping Method</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>Shipping Tracking Number</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
<tr class="odd">
<td>External Asset Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr class="even">
<td>Customer Name</td>
<td>relation</td>
<td>Accounts</td>
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
<tr class="odd">
<td>Last Modified By</td>
<td>52</td>
<td></td>
</tr>
</tbody>
</table>

### Custom Information

### Notes

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
<td>Notes</td>
<td>text</td>
<td></td>
</tr>
</tbody>
</table>
