---
title: 'Quality Claims module'
---

Quality Claims module
=====================

Module to control Quality Claims, used to enforce and document ISO
standards. It should capture the details of the claim, who is attending
it, the date references and the outcome. This module is related with
[Quality Actions
module](http://corebos.org/documentation/doku.php?id=en:extensions:extensions:qualityactions)
where each exact step is recorded.  
---- dataentry ---- name : tsolucio/QualityClaims type : corebos-module
description\_wiki: Module to control Quality Claims, used to enforce and
document ISO standards. It should capture the details of the claim, who
is attending it, the date references and the outcome. This module is
related with [Quality Actions
module](http://corebos.org/documentation/doku.php?id=en:extensions:extensions:qualityactions)
where each exact step is recorded. keywords\_tags :
claims,quality,ISO,standards version : 1.0 homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:qualityclaims>
release\_dt : 2015-12-10 licenses : Vizsage price : 120eur
buyemail\_mail : paypal(at)tsolucio(dot)com distribution : Sale
authorname : JPL TSolucio, S.L. authoremail\_mail :
info(at)tsolucio(dot)com supportemail\_mail : info(at)tsolucio(dot)com

------------------------------------------------------------------------

  

Fields
======

### Quality Claims Information

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
<td>Account Name</td>
<td>relation</td>
<td>Accounts</td>
</tr>
<tr class="even">
<td>Nº de Pedido</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>Entidad Relacionada</td>
<td>relation</td>
<td>Project,HelpDesk</td>
</tr>
<tr class="even">
<td>Claim Status</td>
<td>picklist</td>
<td>--None--</td>
</tr>
<tr class="odd">
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
<tr class="even">
<td>Claim Priority</td>
<td>picklist</td>
<td>Low,Medium,High</td>
</tr>
<tr class="odd">
<td>Emitting Department</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Claim Type</td>
<td>picklist</td>
<td>--None--</td>
</tr>
<tr class="odd">
<td>Responsible</td>
<td>101</td>
<td></td>
</tr>
<tr class="even">
<td>Claim Date</td>
<td>date</td>
<td></td>
</tr>
<tr class="odd">
<td>Receiving Department</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Quality Claim No</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
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
</tbody>
</table>
