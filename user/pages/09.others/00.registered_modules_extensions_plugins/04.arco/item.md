---
title: 'ARCO Module'
---

ARCO Module
===========

Módulo para registrar las incidencias de Acceso, Rectificación,
Cancelación y Oposición para cumplir con la LOPD.  
---- dataentry ---- name : tsolucio/ARCO type : corebos-module
description\_wiki: Módulo para registrar las incidencias de Acceso,
Rectificación, Cancelación y Oposición para cumplir con la LOPD.
keywords\_tags :
lopd,Acceso,Rectificación,Cancelación,Oposición,ARCO,protección,datos,ley
version : 1.0 homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:arco>
release\_dt : 2010-02-27 licenses : Vizsage price : 220eur
buyemail\_mail : paypal(at)tsolucio(dot)com distribution : Sale
authorname : JPL TSolucio, S.L. authoremail\_mail :
info(at)tsolucio(dot)com supportemail\_mail : info(at)tsolucio(dot)com

------------------------------------------------------------------------

  

Fields
======

### ARCO Information

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
<td>Account</td>
<td>relation</td>
<td>Accounts</td>
</tr>
<tr class="odd">
<td>Type</td>
<td>picklist</td>
<td>Acceso,Rectificacion,Cancelacion,Oposicion</td>
</tr>
<tr class="even">
<td>Representation</td>
<td>picklist</td>
<td>Propio Interesado,Representante legal</td>
</tr>
<tr class="odd">
<td>Petition</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Address</td>
<td>text</td>
<td></td>
</tr>
<tr class="odd">
<td>Date</td>
<td>date</td>
<td></td>
</tr>
<tr class="even">
<td>Exercice Status</td>
<td>picklist</td>
<td>Pendiente de atencion,Atendido</td>
</tr>
<tr class="odd">
<td>Access Status</td>
<td>picklist</td>
<td>Registrado,Solicitada concrecion,Resuelta solicitud</td>
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

### Custom Information
