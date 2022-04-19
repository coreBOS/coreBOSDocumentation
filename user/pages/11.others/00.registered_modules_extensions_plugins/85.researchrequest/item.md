---
title: 'Research Request module'
---

Research Request module
=======================

Module to control research or investigation requests, used, for example,
to document quote analysis requests or the study of possible solutions
to problems that appear in the business. This module is related with
[Research Request Actions
module](http://corebos.org/documentation/doku.php?id=en:extensions:extensions:researchrequestactions)
where each exact step is recorded.  
---- dataentry ---- name : tsolucio/ResearchRequest type :
corebos-module description\_wiki: Module to control research or
investigation requests, used, for example, to document quote analysis
requests or the study of possible solutions to problems that appear in
the business. This module is related with [Research Request Actions
module](http://corebos.org/documentation/doku.php?id=en:extensions:extensions:researchrequestactions)
where each exact step is recorded. keywords\_tags :
research,request,quality,ISO,standards,investigation,solution version :
1.0 homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:researchrequest>
release\_dt : 2015-12-09 licenses : Vizsage price : 120eur
buyemail\_mail : paypal(at)tsolucio(dot)com distribution : Sale
authorname : JPL TSolucio, S.L. authoremail\_mail :
info(at)tsolucio(dot)com supportemail\_mail : info(at)tsolucio(dot)com

------------------------------------------------------------------------

  

Fields
======

### Research Request Information

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
<td>Research Request No</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
</tr>
<tr class="odd">
<td>Member of</td>
<td>string</td>
<td></td>
</tr>
<tr class="even">
<td>Title</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>Related Entity</td>
<td>relation</td>
<td>Project,HelpDesk</td>
</tr>
<tr class="even">
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
<tr class="odd">
<td>Product</td>
<td>picklist</td>
<td>--None--</td>
</tr>
<tr class="even">
<td>Priority</td>
<td>picklist</td>
<td>--None--</td>
</tr>
<tr class="odd">
<td>Type</td>
<td>picklist</td>
<td>--None--</td>
</tr>
<tr class="even">
<td>Contract Type</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>Filial</td>
<td>picklist</td>
<td>--None--</td>
</tr>
<tr class="even">
<td>Location Technique</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>Distributor</td>
<td>picklist</td>
<td>--None--</td>
</tr>
<tr class="even">
<td>Request Date</td>
<td>date</td>
<td></td>
</tr>
<tr class="odd">
<td>Finish Date</td>
<td>date</td>
<td></td>
</tr>
<tr class="even">
<td>Department</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>Status</td>
<td>picklist</td>
<td>Creado,En espera,Rechazado,Anulado,Cerrado</td>
</tr>
<tr class="even">
<td>Responsible</td>
<td>picklist</td>
<td>--None--</td>
</tr>
<tr class="odd">
<td>Total Time</td>
<td>string</td>
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
