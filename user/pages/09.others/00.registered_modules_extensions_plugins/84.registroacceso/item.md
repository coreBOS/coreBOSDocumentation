---
title: 'Access Registration module'
---

Access Registration module
==========================

This module records all access different people do upon certain assets.
Necessary for inventory knowledge and legal requirements.  
---- dataentry ---- name : tsolucio/RegAcceso type : corebos-module
description\_wiki: This module records all access different people do
upon certain assets. Necessary for inventory knowledge and legal
requirements. keywords\_tags :
inventory,access,computer,hardware,lopd,files version : 1.0
homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:registroacceso>
release\_dt : 2010-02-27 licenses : Vizsage price : 120eur
buyemail\_mail : paypal(at)tsolucio(dot)com distribution : Sale
authorname : JPL TSolucio, S.L. authoremail\_mail :
info(at)tsolucio(dot)com supportemail\_mail : info(at)tsolucio(dot)com

------------------------------------------------------------------------

  

Fields
======

### LBL\_REGACCESO\_INFORMATION

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
<td>Title</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr class="even">
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
<tr class="odd">
<td>Account Name</td>
<td>relation</td>
<td>Accounts</td>
</tr>
<tr class="even">
<td>Responsable</td>
<td>relation</td>
<td>Empleados,Contacts</td>
</tr>
<tr class="odd">
<td>Fichero</td>
<td>relation</td>
<td>Fichero</td>
</tr>
<tr class="even">
<td>Fecha acceso</td>
<td>date</td>
<td></td>
</tr>
<tr class="odd">
<td>Hora acceso</td>
<td>time</td>
<td></td>
</tr>
<tr class="even">
<td>TipoAcceso</td>
<td>picklist</td>
<td>FisicoTerceros,FisicoNoAuto,FisicoAuto,Otros,ACCESS_OK,ACCESS_NOK_BADDEV,ACCESS_NOK_DESTROY,ACCESS_NOK_DEVRETIRED,ACCESS_NOK_BADUSER,ACCESS_NOK_BADPASS</td>
</tr>
<tr class="odd">
<td>Category</td>
<td>picklist</td>
<td>Acceso,PerdidaLlave,RoboLlave,RoboDoc</td>
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
<td>Soportes</td>
<td>relation</td>
<td>Soportes</td>
</tr>
<tr class="odd">
<td>Categoria</td>
<td>picklist</td>
<td>--None--</td>
</tr>
</tbody>
</table>

### DESCRIPTION

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
