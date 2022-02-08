---
title: 'Physical Support module'
---

Physical Support module
=======================

This asset-like module records all the external devices and support
hardware being used by an account. Necessary for inventory knowledge and
legal requirements.  
---- dataentry ---- name : tsolucio/Soportes type : corebos-module
description\_wiki: This asset-like module records all the external
devices and support hardware being used by an account. Necessary for
inventory knowledge and legal requirements. keywords\_tags :
inventory,support,byod,equipment,usb,storage,lopd version : 1.0
homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:soportes>
release\_dt : 2010-02-27 licenses : Vizsage price : 120eur
buyemail\_mail : paypal(at)tsolucio(dot)com distribution : Sale
authorname : JPL TSolucio, S.L. authoremail\_mail :
info(at)tsolucio(dot)com supportemail\_mail : info(at)tsolucio(dot)com

------------------------------------------------------------------------

  

Fields
======

### LBL\_SOPORTES\_INFORMATION

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
<td>registro_no</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr class="even">
<td>soporte_no</td>
<td>autonumber</td>
<td></td>
</tr>
<tr class="odd">
<td>Tipo</td>
<td>picklist</td>
<td>Pen Drive USB,CD,DVD,ZIP,HD USB,Cinta DAT,Disquete 3,5,PDA,Armario / Archivador Bajo Llave,Soporte Papel,SAN,HD EXTERNO</td>
</tr>
<tr class="even">
<td>Contenido</td>
<td>picklist</td>
<td>Copia de Seguridad,Listados,Doc. Trabajo,Correo Electrónico,Expedientes Académicos,Expediente Laboral,Doc. Proveedores,Doc. Fiscal / Contable,Doc. Calidad,Informes Psicopedagógicos,Información alumnos</td>
</tr>
<tr class="odd">
<td>Ubicacion</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Fecha de Alta</td>
<td>date</td>
<td></td>
</tr>
<tr class="odd">
<td>Soporte Movil</td>
<td>checkbox</td>
<td></td>
</tr>
<tr class="even">
<td>Texto Soporte Movil</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>RespSeg</td>
<td>relation</td>
<td>Contacts,Empleados</td>
</tr>
<tr class="even">
<td>Medidas de seguridad adicionales adoptadas</td>
<td>string</td>
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
<tr class="odd">
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
<tr class="even">
<td>Description</td>
<td>text</td>
<td></td>
</tr>
<tr class="odd">
<td>tovalidate</td>
<td>checkbox</td>
<td></td>
</tr>
<tr class="even">
<td>Destruido</td>
<td>checkbox</td>
<td></td>
</tr>
<tr class="odd">
<td>Cuenta</td>
<td>relation</td>
<td>Accounts</td>
</tr>
<tr class="even">
<td>Plantilla</td>
<td>relation</td>
<td>Documents</td>
</tr>
<tr class="odd">
<td>NumSerie</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Borrar contenido</td>
<td>checkbox</td>
<td></td>
</tr>
</tbody>
</table>

### Custom Information

### Discontinued Information

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
<td>MetodoDestruccion</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>DestInfo</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>Fecha de baja</td>
<td>date</td>
<td></td>
</tr>
</tbody>
</table>

### Clave de cifrado

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
<td>Clave de cifrado</td>
<td>text</td>
<td></td>
</tr>
</tbody>
</table>
