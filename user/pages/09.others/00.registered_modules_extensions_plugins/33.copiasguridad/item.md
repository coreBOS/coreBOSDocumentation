---
title: 'Backup Procedure module'
---

Backup Procedure module
=======================

This documentation-like module records all the backups systems and their
responsible parties that are used in the account. Necessary for
inventory knowledge and legal requirements.  
---- dataentry ---- name : tsolucio/CpSeg type : corebos-module
description\_wiki: This documentation-like module records all the
backups systems and their responsible parties that are used in the
account. Necessary for inventory knowledge and legal requirements.
keywords\_tags : inventory,copias,seguridad,backup,lopd version : 1.0
homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:copiaseguridad>
release\_dt : 2010-02-27 licenses : Vizsage price : 120eur
buyemail\_mail : paypal(at)tsolucio(dot)com distribution : Sale
authorname : JPL TSolucio, S.L. authoremail\_mail :
info(at)tsolucio(dot)com supportemail\_mail : info(at)tsolucio(dot)com

------------------------------------------------------------------------

  

Fields
======

### Backup Information

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
<td>Backup No</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
</tr>
<tr class="even">
<td>Procedure Name</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>Account</td>
<td>relation</td>
<td>Accounts</td>
</tr>
<tr class="even">
<td>Copied data</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>Procedure description</td>
<td>text</td>
<td></td>
</tr>
<tr class="even">
<td>Frequency</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>Backup Location</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Person or area in charge of procedure</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>Template</td>
<td>relation</td>
<td>Documents</td>
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
