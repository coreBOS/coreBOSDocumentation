---
title: 'Adequacy: Steps module'
---

Adequacy: Steps module
======================

This module is part of the [Adequacy
functionality](http://corebos.org/documentation/doku.php?id=en:extensions:extensions:adecuaciones).
It represents a pool of steps or actions that can be done in any given
adequacy project. The
[flow](http://corebos.org/documentation/doku.php?id=en:extensions:extensions:flujo)
module will group these steps together into sequences to be used.  
---- dataentry ---- name : tsolucio/Pasos type : corebos-module
description\_wiki: This module is part of the [Adequacy
functionality](http://corebos.org/documentation/doku.php?id=en:extensions:extensions:adecuaciones).
It represents a pool of steps or actions that can be done in any given
adequacy project. The
[flow](http://corebos.org/documentation/doku.php?id=en:extensions:extensions:flujo)
module will group these steps together into sequences to be used.
keywords\_tags : project,steps,process,implementation,adapt version :
1.0 homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:pasos>
release\_dt : 2010-03-03 licenses : Vizsage price : 120eur
buyemail\_mail : paypal(at)tsolucio(dot)com distribution : Sale
authorname : JPL TSolucio, S.L. authoremail\_mail :
info(at)tsolucio(dot)com supportemail\_mail : info(at)tsolucio(dot)com

------------------------------------------------------------------------

  

Fields
======

### Step Information

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
<td>Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr class="even">
<td>Status</td>
<td>picklist</td>
<td>-----,Terminado</td>
</tr>
<tr class="odd">
<td>Required</td>
<td>checkbox</td>
<td></td>
</tr>
<tr class="even">
<td>Duration</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>Template</td>
<td>relation</td>
<td>Documents</td>
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
<tr class="even">
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
</tbody>
</table>

### Custom Information

### Step Description

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
