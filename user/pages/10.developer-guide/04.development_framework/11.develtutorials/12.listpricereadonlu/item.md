---
title: 'How to Make List Price Read Only On Inventory Modules'
metadata:
    description: 'How to Make List Price Read Only On Inventory Modules'
    author: 'Joe Bordes'
content:
    items:
        - '@self.children'
    limit: 5
    order:
        by: date
        dir: desc
    pagination: true
    url_taxonomy_filters: true
taxonomy:
    category:
        - development
        - inventory
    tag:
        - read only
        - list price
        - inventory
---

<div class="notices red">This can now be done using the <strong>Inventory_ListPrice_ReadOnly</strong> global variable</div>

===

Our friend and supporter **[David Fernandez](https://plus.google.com/u/0/105123673241771874278)** has
created and shared a change to make the price list input box read only so users cannot change the value set by the application.

**THANK YOU David!!**

Patch file can be [downloaded from this link](https://discussions.corebos.org/documentation/lib/exe/fetch.php?media=devel:patches:makepricelistreadonlyoninventorymodules.diff) and
seen in the next patch:

```php

diff --git a/Smarty/templates/Inventory/ProductDetails.tpl b/Smarty/templates/Inventory/ProductDetails.tpl
index afb23e0..1629aa5 100644
--- a/Smarty/templates/Inventory/ProductDetails.tpl
+++ b/Smarty/templates/Inventory/ProductDetails.tpl
@@ -207,7 +207,7 @@ function displayCoords(currObj,obj,mode,curr_row)
 		<table width="100%" cellpadding="0" cellspacing="0">
 		   <tr>
 			<td align="right">
-				<input id="listPrice1" name="listPrice1" value="{$UNIT_PRICE}" type="text" class="small " style="width:70px" onBlur="calcTotal();setDiscount(this,'1'); callTaxCalc(1);calcTotal();"/>&nbsp;<img src="{'pricebook.gif'|@vtiger_imageurl:$THEME}" onclick="priceBookPickList(this,1)">
+				<input readonly id="listPrice1" name="listPrice1" value="{$UNIT_PRICE}" type="text" class="small " style="width:70px" onBlur="calcTotal();setDiscount(this,'1'); callTaxCalc(1);calcTotal();"/>&nbsp;<img src="{'pricebook.gif'|@vtiger_imageurl:$THEME}" onclick="priceBookPickList(this,1)">
 			</td>
 		   </tr>
 		   <tr>
diff --git a/Smarty/templates/Inventory/ProductDetailsEditView.tpl b/Smarty/templates/Inventory/ProductDetailsEditView.tpl
index cf77543..fdcdb0b 100755
--- a/Smarty/templates/Inventory/ProductDetailsEditView.tpl
+++ b/Smarty/templates/Inventory/ProductDetailsEditView.tpl
@@ -245,7 +245,7 @@ function displayCoords(currObj,obj,mode,curr_row)
 		<table width="100%" cellpadding="0" cellspacing="0">
 		   <tr>
 			<td align="right">
-				<input id="{$listPrice}" name="{$listPrice}" value="{$data.$listPrice}" type="text" class="small " style="width:70px" onBlur="calcTotal(); setDiscount(this,'{$row_no}');callTaxCalc('{$row_no}');"/>&nbsp;<img src="{'pricebook.gif'|@vtiger_imageurl:$THEME}" onclick="priceBookPickList(this,'{$row_no}')">
+				<input readonly id="{$listPrice}" name="{$listPrice}" value="{$data.$listPrice}" type="text" class="small " style="width:70px" onBlur="calcTotal(); setDiscount(this,'{$row_no}');callTaxCalc('{$row_no}');"/>&nbsp;<img src="{'pricebook.gif'|@vtiger_imageurl:$THEME}" onclick="priceBookPickList(this,'{$row_no}')">
 			</td>
 		   </tr>
 		   <tr>
diff --git a/include/js/Inventory.js b/include/js/Inventory.js
index 2836c99..47e5d07 100644
--- a/include/js/Inventory.js
+++ b/include/js/Inventory.js
@@ -679,7 +679,7 @@ function fnAddProductRow(module,image_path){
 	colfour.innerHTML=temp;
 	//List Price with Discount, Total after Discount and Tax labels
 	colfive.className = "crmTableRow small"
-	colfive.innerHTML='<table width="100%" cellpadding="0" cellspacing="0"><tr><td align="right"><input id="listPrice'+count+'" name="listPrice'+count+'" value="0.00" type="text" class="small " style="width:70px" onBlur="calcTotal();setDiscount(this,'+count+');callTaxCalc('+count+'); calcTotal();"/>&nbsp;<img src="themes/images/pricebook.gif" onclick="priceBookPickList(this,'+count+')"></td></tr><tr><td align="right" style="padding:5px;" nowrap>	(-)&nbsp;<b><a href="javascript:doNothing();" onClick="displayCoords(this,\'discount_div'+count+'\',\'discount\','+count+')" >'+product_labelarr.DISCOUNT+'</a> : </b><div class=\"discountUI\" id=\"discount_div'+count+'"><input type="hidden" id="discount_type'+count+'" name="discount_type'+count+'" value=""><table width="100%" border="0" cellpadding="5" cellspacing="0" class="small"><tr><td id="discount_div_title'+count+'" nowrap align="left" ></td><td align="right"><img src="themes/images/close.gif" border="0" onClick="fnHidePopDiv(\'discount_div'+count+'\')" style="cursor:pointer;"></td></tr><tr><td align="left" class="lineOnTop"><input type="radio" name="discount'+count+'" checked onclick="setDiscount(this,'+count+'); callTaxCalc('+count+');calcTotal();">&nbsp; '+product_labelarr.ZERO_DISCOUNT+'</td><td class="lineOnTop">&nbsp;</td></tr><tr><td align="left"><input type="radio" name="discount'+count+'" onclick="setDiscount(this,'+count+'); callTaxCalc('+count+');calcTotal();">&nbsp; % '+product_labelarr.PERCENT_OF_PRICE+' </td><td align="right"><input type="text" class="small" size="2" id="discount_percentage'+count+'" name="discount_percentage'+count+'" value="0" style="visibility:hidden" onBlur="setDiscount(this,'+count+'); callTaxCalc('+count+');calcTotal();">&nbsp;%</td></tr><tr><td align="left" nowrap><input type="radio" name="discount'+count+'" onclick="setDiscount(this,'+count+'); callTaxCalc('+count+');calcTotal();">&nbsp; '+product_labelarr.DIRECT_PRICE_REDUCTION+'</td><td align="right"><input type="text" id="discount_amount'+count+'" name="discount_amount'+count+'" size="5" value="0" style="visibility:hidden" onBlur="setDiscount(this,'+count+'); callTaxCalc('+count+');calcTotal();"></td></tr></table></div></td></tr><tr> <td align="right" style="padding:5px;" nowrap><b>'+product_labelarr.TOTAL_AFTER_DISCOUNT+' :</b></td></tr><tr id="individual_tax_row'+count+'" class="TaxShow"><td align="right" style="padding:5px;" nowrap>(+)&nbsp;<b><a href="javascript:doNothing();" onClick="displayCoords(this,\'tax_div'+count+'\',\'tax\','+count+')" >'+product_labelarr.TAX+' </a> : </b><div class="discountUI" id="tax_div'+count+'"></div></td></tr></table> ';
+	colfive.innerHTML='<table width="100%" cellpadding="0" cellspacing="0"><tr><td align="right"><input readonly id="listPrice'+count+'" name="listPrice'+count+'" value="0.00" type="text" class="small " style="width:70px" onBlur="calcTotal();setDiscount(this,'+count+');callTaxCalc('+count+'); calcTotal();"/>&nbsp;<img src="themes/images/pricebook.gif" onclick="priceBookPickList(this,'+count+')"></td></tr><tr><td align="right" style="padding:5px;" nowrap>		(-)&nbsp;<b><a href="javascript:doNothing();" onClick="displayCoords(this,\'discount_div'+count+'\',\'discount\','+count+')" >'+product_labelarr.DISCOUNT+'</a> : </b><div class=\"discountUI\" id=\"discount_div'+count+'"><input type="hidden" id="discount_type'+count+'" name="discount_type'+count+'" value=""><table width="100%" border="0" cellpadding="5" cellspacing="0" class="small"><tr><td id="discount_div_title'+count+'" nowrap align="left" ></td><td align="right"><img src="themes/images/close.gif" border="0" onClick="fnHidePopDiv(\'discount_div'+count+'\')" style="cursor:pointer;"></td></tr><tr><td align="left" class="lineOnTop"><input type="radio" name="discount'+count+'" checked onclick="setDiscount(this,'+count+'); callTaxCalc('+count+');calcTotal();">&nbsp; '+product_labelarr.ZERO_DISCOUNT+'</td><td class="lineOnTop">&nbsp;</td></tr><tr><td align="left"><input type="radio" name="discount'+count+'" onclick="setDiscount(this,'+count+'); callTaxCalc('+count+');calcTotal();">&nbsp; % '+product_labelarr.PERCENT_OF_PRICE+' </td><td align="right"><input type="text" class="small" size="2" id="discount_percentage'+count+'" name="discount_percentage'+count+'" value="0" style="visibility:hidden" onBlur="setDiscount(this,'+count+'); callTaxCalc('+count+');calcTotal();">&nbsp;%</td></tr><tr><td align="left" nowrap><input type="radio" name="discount'+count+'" onclick="setDiscount(this,'+count+'); callTaxCalc('+count+');calcTotal();">&nbsp; '+product_labelarr.DIRECT_PRICE_REDUCTION+'</td><td align="right"><input type="text" id="discount_amount'+count+'" name="discount_amount'+count+'" size="5" value="0" style="visibility:hidden" onBlur="setDiscount(this,'+count+'); callTaxCalc('+count+');calcTotal();"></td></tr></table></div></td></tr><tr> <td align="right" style="padding:5px;" nowrap><b>'+product_labelarr.TOTAL_AFTER_DISCOUNT+' :</b></td></tr><tr id="individual_tax_row'+count+'" class="TaxShow"><td align="right" style="padding:5px;" nowrap>(+)&nbsp;<b><a href="javascript:doNothing();" onClick="displayCoords(this,\'tax_div'+count+'\',\'tax\','+count+')" >'+product_labelarr.TAX+' </a> : </b><div class="discountUI" id="tax_div'+count+'"></div></td></tr></table> ';
 
 	//Total and Discount, Total after Discount and Tax details
 	colsix.className = "crmTableRow small"
diff --git a/modules/Services/Services.js b/modules/Services/Services.js
index 3d99296..bc73f1f 100644
--- a/modules/Services/Services.js
+++ b/modules/Services/Services.js
@@ -297,7 +297,7 @@ function fnAddServiceRow(module,image_path){
 	colfour.innerHTML=temp;
 	//List Price with Discount, Total after Discount and Tax labels
 	colfive.className = "crmTableRow small"
-	colfive.innerHTML='<table width="100%" cellpadding="0" cellspacing="0"><tr><td align="right"><input id="listPrice'+count+'" name="listPrice'+count+'" value="0.00" type="text" class="small " style="width:70px" onBlur="calcTotal();setDiscount(this,'+count+');callTaxCalc('+count+'); calcTotal();"/>&nbsp;<img src="themes/images/pricebook.gif" onclick="priceBookPickList(this,'+count+')"></td></tr><tr><td align="right" style="padding:5px;" nowrap>	(-)&nbsp;<b><a href="javascript:doNothing();" onClick="displayCoords(this,\'discount_div'+count+'\',\'discount\','+count+')" >'+product_labelarr.DISCOUNT+'</a> : </b><div class=\"discountUI\" id=\"discount_div'+count+'"><input type="hidden" id="discount_type'+count+'" name="discount_type'+count+'" value=""><table width="100%" border="0" cellpadding="5" cellspacing="0" class="small"><tr><td id="discount_div_title'+count+'" nowrap align="left" ></td><td align="right"><img src="themes/images/close.gif" border="0" onClick="fnHidePopDiv(\'discount_div'+count+'\')" style="cursor:pointer;"></td></tr><tr><td align="left" class="lineOnTop"><input type="radio" name="discount'+count+'" checked onclick="setDiscount(this,'+count+'); callTaxCalc('+count+');calcTotal();">&nbsp; '+product_labelarr.ZERO_DISCOUNT+'</td><td class="lineOnTop">&nbsp;</td></tr><tr><td align="left"><input type="radio" name="discount'+count+'" onclick="setDiscount(this,'+count+'); callTaxCalc('+count+');calcTotal();">&nbsp; % '+product_labelarr.PERCENT_OF_PRICE+' </td><td align="right"><input type="text" class="small" size="2" id="discount_percentage'+count+'" name="discount_percentage'+count+'" value="0" style="visibility:hidden" onBlur="setDiscount(this,'+count+'); callTaxCalc('+count+');calcTotal();">&nbsp;%</td></tr><tr><td align="left" nowrap><input type="radio" name="discount'+count+'" onclick="setDiscount(this,'+count+'); callTaxCalc('+count+');calcTotal();">&nbsp; '+product_labelarr.DIRECT_PRICE_REDUCTION+'</td><td align="right"><input type="text" id="discount_amount'+count+'" name="discount_amount'+count+'" size="5" value="0" style="visibility:hidden" onBlur="setDiscount(this,'+count+'); callTaxCalc('+count+');calcTotal();"></td></tr></table></div></td></tr><tr> <td align="right" style="padding:5px;" nowrap><b>'+product_labelarr.TOTAL_AFTER_DISCOUNT+' :</b></td></tr><tr id="individual_tax_row'+count+'" class="TaxShow"><td align="right" style="padding:5px;" nowrap>(+)&nbsp;<b><a href="javascript:doNothing();" onClick="displayCoords(this,\'tax_div'+count+'\',\'tax\','+count+')" >'+product_labelarr.TAX+' </a> : </b><div class="discountUI" id="tax_div'+count+'"></div></td></tr></table> ';
+	colfive.innerHTML='<table width="100%" cellpadding="0" cellspacing="0"><tr><td align="right"><input readonly id="listPrice'+count+'" name="listPrice'+count+'" value="0.00" type="text" class="small " style="width:70px" onBlur="calcTotal();setDiscount(this,'+count+');callTaxCalc('+count+'); calcTotal();"/>&nbsp;<img src="themes/images/pricebook.gif" onclick="priceBookPickList(this,'+count+')"></td></tr><tr><td align="right" style="padding:5px;" nowrap>		(-)&nbsp;<b><a href="javascript:doNothing();" onClick="displayCoords(this,\'discount_div'+count+'\',\'discount\','+count+')" >'+product_labelarr.DISCOUNT+'</a> : </b><div class=\"discountUI\" id=\"discount_div'+count+'"><input type="hidden" id="discount_type'+count+'" name="discount_type'+count+'" value=""><table width="100%" border="0" cellpadding="5" cellspacing="0" class="small"><tr><td id="discount_div_title'+count+'" nowrap align="left" ></td><td align="right"><img src="themes/images/close.gif" border="0" onClick="fnHidePopDiv(\'discount_div'+count+'\')" style="cursor:pointer;"></td></tr><tr><td align="left" class="lineOnTop"><input type="radio" name="discount'+count+'" checked onclick="setDiscount(this,'+count+'); callTaxCalc('+count+');calcTotal();">&nbsp; '+product_labelarr.ZERO_DISCOUNT+'</td><td class="lineOnTop">&nbsp;</td></tr><tr><td align="left"><input type="radio" name="discount'+count+'" onclick="setDiscount(this,'+count+'); callTaxCalc('+count+');calcTotal();">&nbsp; % '+product_labelarr.PERCENT_OF_PRICE+' </td><td align="right"><input type="text" class="small" size="2" id="discount_percentage'+count+'" name="discount_percentage'+count+'" value="0" style="visibility:hidden" onBlur="setDiscount(this,'+count+'); callTaxCalc('+count+');calcTotal();">&nbsp;%</td></tr><tr><td align="left" nowrap><input type="radio" name="discount'+count+'" onclick="setDiscount(this,'+count+'); callTaxCalc('+count+');calcTotal();">&nbsp; '+product_labelarr.DIRECT_PRICE_REDUCTION+'</td><td align="right"><input type="text" id="discount_amount'+count+'" name="discount_amount'+count+'" size="5" value="0" style="visibility:hidden" onBlur="setDiscount(this,'+count+'); callTaxCalc('+count+');calcTotal();"></td></tr></table></div></td></tr><tr> <td align="right" style="padding:5px;" nowrap><b>'+product_labelarr.TOTAL_AFTER_DISCOUNT+' :</b></td></tr><tr id="individual_tax_row'+count+'" class="TaxShow"><td align="right" style="padding:5px;" nowrap>(+)&nbsp;<b><a href="javascript:doNothing();" onClick="displayCoords(this,\'tax_div'+count+'\',\'tax\','+count+')" >'+product_labelarr.TAX+' </a> : </b><div class="discountUI" id="tax_div'+count+'"></div></td></tr></table> ';
 
 	//Total and Discount, Total after Discount and Tax details
 	colsix.className = "crmTableRow small"
```