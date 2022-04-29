---
title: 'Adequacy module'
---

Adequacy module
===============

This project-like module is part of the Adequacy functionality. It
represents the actual implementation process in the company designated
by the
[flow](http://corebos.org/documentation/doku.php?id=en:extensions:extensions:flujo)
and
[steps](http://corebos.org/documentation/doku.php?id=en:extensions:extensions:pasos)
and controls the status of implementation of the adequacy project.  
---- dataentry ---- name : tsolucio/Adecuaciones type : corebos-module
description\_wiki: This project-like module is part of the Adequacy
functionality. It represents the actual implementation process in the
company designated by the
[flow](http://corebos.org/documentation/doku.php?id=en:extensions:extensions:flujo)
and
[steps](http://corebos.org/documentation/doku.php?id=en:extensions:extensions:pasos)
and controls the status of implementation of the adequacy project.
keywords\_tags : project,steps,process,implementation,adapt version :
1.0 homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:adecuaciones>
release\_dt : 2010-03-03 licenses : Vizsage price : 120eur
buyemail\_mail : paypal(at)tsolucio(dot)com distribution : Sale
authorname : JPL TSolucio, S.L. authoremail\_mail :
info(at)tsolucio(dot)com supportemail\_mail : info(at)tsolucio(dot)com

------------------------------------------------------------------------

  

Fields
======

### Adecuations Information

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
<td>Start Date</td>
<td>date</td>
<td></td>
</tr>
<tr class="odd">
<td>End Date</td>
<td>date</td>
<td></td>
</tr>
<tr class="even">
<td>State</td>
<td>picklist</td>
<td>-----,Terminado</td>
</tr>
<tr class="odd">
<td>Paso Actual</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>% Realizacion</td>
<td>number</td>
<td></td>
</tr>
<tr class="odd">
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
<tr class="even">
<td>Account Name</td>
<td>relation</td>
<td>Accounts</td>
</tr>
<tr class="odd">
<td>Flujo de Trabajo</td>
<td>relation</td>
<td>Flujo</td>
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

### Customer Information

### Adecuations Description

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
