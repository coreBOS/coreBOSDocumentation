---
title: 'Equipment module'
---

Equipment module
================

This asset-like module records all computers being used by an account.
Necessary for inventory knowledge and legal requirements.  
---- dataentry ---- name : tsolucio/Equipos type : corebos-module
description\_wiki: This asset-like module records all computers being
used by an account. Necessary for inventory knowledge and legal
requirements. keywords\_tags :
inventory,equipment,computer,hardware,lopd version : 1.0 homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:equipos>
release\_dt : 2010-02-27 licenses : Vizsage price : 120eur
buyemail\_mail : paypal(at)tsolucio(dot)com distribution : Sale
authorname : JPL TSolucio, S.L. authoremail\_mail :
info(at)tsolucio(dot)com supportemail\_mail : info(at)tsolucio(dot)com

------------------------------------------------------------------------

  

Fields
======

### Información

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
<td>Nombre</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr class="even">
<td>CPU</td>
<td>picklist</td>
<td>Pentium III,Celeron,Intel Dual Core,AMDAthlon,AMDAthlon64,AMDSempron,Intel Xeon,Intel x86,Intel Core 2 Duo,Intel Core I 7,Centrino,Pentium D,Intel Core I 3,Intel Core I 5,Intel Atom,Qualcomm,AMD Turion X2 Dual Core,AMD Duron,AMD Athlon,Intel Core Quad,Intel Core 2,Int. Celeron,Intel Centrino,Pentium Dual Core,Pentium IV,Intel Celeron,Intel T2060,PowerPC,Pentium II,</td>
</tr>
<tr class="odd">
<td>RAM</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>NumDiscos</td>
<td>picklist</td>
<td>1,2,3,4,5,6,</td>
</tr>
<tr class="odd">
<td>Capacidad</td>
<td>picklist</td>
<td>20 GB,40 GB,60 GB,80 GB,120 GB,160 GB,250 GB,320 GB,500 GB,750 GB,1TB,200 GB,240 GB,,300 GB</td>
</tr>
<tr class="even">
<td>Internet</td>
<td>checkbox</td>
<td></td>
</tr>
<tr class="odd">
<td>Sist. Op.</td>
<td>picklist</td>
<td>Windows 7,Windows 2000,Windows ME,Windows XP Home,Windows XP Prof.,Windos Vista,GNU/Linux,MACOSX,Windows Server 2003,Windows Server 2008,MS-DOS,Windows 98,BlackBerry OS,Windows 2003 Server SP2,Ubuntu 8.04,Windows XP Prof. SP3,Ubuntu 10.04,Windows XP Prof. SP2,Windows Vista Home,XP Profesional SP3,--,Windows 2000 Advanced Server,</td>
</tr>
<tr class="even">
<td>Versión</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>ActAutomaticas</td>
<td>checkbox</td>
<td></td>
</tr>
<tr class="even">
<td>Antivirus</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>Firewall</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Funcion</td>
<td>picklist</td>
<td>Puesto de trabajo/Sobremesa,Portátil,Servidor,Servidor archivos,Servidor aplicaciones,Servidor comunicaciones,Servidor correo,Servidor WEB,PC Sobremesa,PDA / SmartPhone,Servidor,Servidor Copia,Servidor de Dominio,Direccion,Secretaria,Direccion,Administracion,Gabinete,Gabinete portatil,Dep. Pastoral,Dep. Deportes,Jefe Estudios,Sala profesores,Aula refuerzo (ant.musica),Francesc,Paco Manchon,Infantil3A,Infantil3B,Infantil4A,Infantil4B,Infantil5A,Infantil5B,1A,1B,1C,2A,2B,2C,3A,3B,3C,4A,4B,4C,5A,5B,5C,6A,6B,6C,1er. Ciclo,2o Ciclo,--,Servidor correo,Servidor aplicaciones,Servidor DHCP</td>
</tr>
<tr class="odd">
<td>Marca</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Modelo</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>NumSerie</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Plantilla</td>
<td>relation</td>
<td>Documents</td>
</tr>
<tr class="odd">
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
<tr class="even">
<td>Fecha Alta</td>
<td>date</td>
<td></td>
</tr>
<tr class="odd">
<td>Fecha Baja</td>
<td>date</td>
<td></td>
</tr>
<tr class="even">
<td>LBL_TOVALIDATE</td>
<td>checkbox</td>
<td></td>
</tr>
<tr class="odd">
<td>Destruido</td>
<td>checkbox</td>
<td></td>
</tr>
<tr class="even">
<td>Description</td>
<td>text</td>
<td></td>
</tr>
<tr class="odd">
<td>UbicacionFisica</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>ConexionInternet</td>
<td>picklist</td>
<td>SI,NO,1,0,</td>
</tr>
<tr class="odd">
<td>LAN</td>
<td>picklist</td>
<td>SI,NO,1,0,</td>
</tr>
<tr class="even">
<td>Usuario</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>Medidas de Seguridad Aplicadas</td>
<td>picklist</td>
<td>Nivel Basico,Nivel Medio,Nivel Alto</td>
</tr>
<tr class="even">
<td>Aplicaciones de Tratamiento</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>FicherosFisicosTratados</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Cuenta</td>
<td>relation</td>
<td>Accounts</td>
</tr>
<tr class="odd">
<td>Equipo BYOD</td>
<td>checkbox</td>
<td></td>
</tr>
</tbody>
</table>
