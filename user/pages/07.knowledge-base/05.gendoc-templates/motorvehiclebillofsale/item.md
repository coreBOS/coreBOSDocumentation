---
title: 'GenDoc Template:: Motor Vehicle Bill of Sale'
---

GenDoc Template:: Motor Vehicle Bill of Sale
--------------------------------------------

Motor Vehicle Bill of Sale transaction template.

---- dataentry ---- name : motorvehiclebillofsale type : gendoctemplate
template\_img : :en:gendoc:templatestore:motorvehiclebillofsale.odt
pdfexample\_img: :en:gendoc:templatestore:motorvehiclebillofsale.pdf
description\_wiki: Motor Vehicle Bill of Sale transaction template.
keywords\_tags : sell,sale,bill,invoice,contract,transaction,vehicle,car
language: en module: Invoice version : 1.0 release\_dt : 2018-01-13
licenses : CC price : Free distribution : Free authorname : Joe Bordes
joe(at)tsolucio(dot)com

------------------------------------------------------------------------

  
This template requires adding custom fields on the Invoice and Product.

The goal of the template is to document the transaction of selling a
car. We need some specific information of the vehicle and about the
transaction.

The vehicle information will be on products and the transaction will be
an invoice. On the **Invoice** we add:

<table>
<tbody>
<tr class="odd">
<td>Down Payment:</td>
<td>{Invoice.cf_1227}</td>
</tr>
<tr class="even">
<td>Transfer days:</td>
<td>{Invoice.cf_1228}</td>
</tr>
<tr class="odd">
<td>Inspection Days:</td>
<td>{Invoice.cf_1229}</td>
</tr>
<tr class="even">
<td>Retain Amount:</td>
<td>{Invoice.cf_1230}</td>
</tr>
</tbody>
</table>

and on the **Products** we add:

<table>
<tbody>
<tr class="odd">
<td>VIN:</td>
<td>{Products.cf_1219}</td>
</tr>
<tr class="even">
<td>Make:</td>
<td>{Products.cf_1220}</td>
</tr>
<tr class="odd">
<td>Model:</td>
<td>{Products.cf_1221}</td>
</tr>
<tr class="even">
<td>Color:</td>
<td>{Products.cf_1222}</td>
</tr>
<tr class="odd">
<td>Style:</td>
<td>{Products.cf_1223}</td>
</tr>
<tr class="even">
<td>Year:</td>
<td>{Products.cf_1224}</td>
</tr>
<tr class="odd">
<td>Odometer:</td>
<td>{Products.cf_1225}</td>
</tr>
<tr class="even">
<td>TitleN:</td>
<td>{Products.cf_1226}</td>
</tr>
</tbody>
</table>

Obviously the numbers assigned to your fields will be different and you
will have to edit the template accordingly
