---
title: 'Register Backups module'
---

Register Backups module
=======================

This module records all the backups that have been done. Necessary for
inventory knowledge and legal requirements.  
---- dataentry ---- name : tsolucio/RegCpSeg type : corebos-module
description\_wiki: This module records all the backups that have been
done. Necessary for inventory knowledge and legal requirements.
keywords\_tags : inventory,copias,seguridad,backup,lopd,record,register
version : 1.0 homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:registercopiaseguridad>
release\_dt : 2010-02-27 licenses : Vizsage price : 120eur
buyemail\_mail : paypal(at)tsolucio(dot)com distribution : Sale
authorname : JPL TSolucio, S.L. authoremail\_mail :
info(at)tsolucio(dot)com supportemail\_mail : info(at)tsolucio(dot)com

------------------------------------------------------------------------

  

Fields
======

### Incident Information

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
<tr class="even">
<td>Description</td>
<td>text</td>
<td></td>
</tr>
<tr class="odd">
<td>Identificacion</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Frecuencia</td>
<td>picklist</td>
<td>No,Diaria,Semanal,Quincenal,Semanas Pares,Semanas Impares,Mensual,Trimestral,Anual</td>
</tr>
<tr class="odd">
<td>ProcedimientoRealizacion</td>
<td>text</td>
<td></td>
</tr>
<tr class="even">
<td>ProcedimientoRecuperacion</td>
<td>text</td>
<td></td>
</tr>
<tr class="odd">
<td>Ubicacion</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>UsuariosAutorizados</td>
<td>relation</td>
<td>Empleados,Contacts,Vendors</td>
</tr>
<tr class="odd">
<td>Title</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
</tr>
<tr class="even">
<td>Account</td>
<td>relation</td>
<td>Accounts</td>
</tr>
<tr class="odd">
<td>StartTime</td>
<td>datetime (internal)</td>
<td></td>
</tr>
<tr class="even">
<td>Nodisponible</td>
<td>checkbox</td>
<td></td>
</tr>
<tr class="odd">
<td>Plantilla</td>
<td>relation</td>
<td>Documents</td>
</tr>
<tr class="even">
<td>execProc</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>CopiaCifrada</td>
<td>picklist</td>
<td>Si,No</td>
</tr>
<tr class="even">
<td>Soportes</td>
<td>relation</td>
<td>Soportes</td>
</tr>
<tr class="odd">
<td>Fichero</td>
<td>relation</td>
<td>Fichero</td>
</tr>
</tbody>
</table>

### Description Information

### Solution Information
