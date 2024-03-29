---
title: 'Popup open hook'
metadata:
    description: 'This hook permits us to customize the action that will be taken when a user clicks on the select icon of a uitype10/capture field.'
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
        - event
    tag:
        - hooks
        - popup
---

## Popup open hook

This hook permits us to customize the action that will be taken when a user clicks on the select icon of a uitype10/capture field.

===

The need for this type of hook appears basically when we want to add some special filtering or conditions on the records that will appear in the popup screen. Normally this will be because we have a dependency between the records of the popup module and the underlying module, in such a way that we can restrict the records shown to a subset of records that will be related.

The typical example that the application already implements is to show only the contacts related to the selected account on an invoice.

The code that needs to be added to restrict the selection of records is explained in the 
[How to open a capture popup with a preselected set of records](../../../10.developer-guide/04.development_framework/11.develtutorials/19.conditional_popup) article, so here we will explain how to add the hook and see an example.

This hook consists in changing the javascript function that will be called when the user clicks on the select icon. To do this we need to:

1. define the new javascript function that will be called
2. insert the javascript file that contains our new function in the HEADERSCRIPT hook to make it available
3. register the function for the capture field in the module that appears in the popup

### define new javascript function

We can create a new javascript file which will hold our function or use the existing javascript file for our module. In either case we simply add our function being careful that the function name will not collide with existing functions.

The parameters the function will get are:

- **fromlink:** 'qcreate' or empty depending on the form the capture field is
- **fldname:** the name of the field
- **MODULE:** the underlying module active on screen
- **ID:** the crmid of the record being edited, will be empty when creating

with this information and being able to access all the fields on the form via javascript, we can decide if we need to continue or simply pass the work to be done to the default 'vtlib_open_popup_window' function.

If we do have to continue, we should finish the execution opening the popup window for selection to maintain consistency but we could decide to restrict the capture for some reasons and simply show a message to the user (for example).

### insert the javascript file (HEADERSCRIPT)
We use the **addLink** method with type **HEADERSCRIPT** to register our javascript code into the application:

```php 
$module->addLink('HEADERSCRIPT','your_script.js',"path/to/your/script.js");
```

[See the addLink helper script](../../04.development_framework/06.helperscripts)

### Register the function for the capture field

To do this we simply have to define a new method in our module that will return the name of the function to be called. The method is **getvtlib_open_popup_window_function**. It will receive these parameters:

- **field name:** name of the capture field
- **base module:** name of the module the field is on

With these two parameters we can decide which javascript function to call. Since we have the exact name and on which module the field is, we could even call different functions depending on the module.

This method **MUST** return a value, always. In case of not wanting to execute any function you must return the default function: **vtlib_open_popup_window** 

## TLDR; Show me the code

### Example: basic search

This example will modify the product capture field on Assets, so it lists only those products that contain the text "Pack".

1. **define the new javascript function that will be called**

 Create the script modules/Assets/assetcapture.js (it could be anywhere really)

 ```php
function productCaptureOnAssets(fromlink,fldname,MODULE,ID) {
	var BasicSearch = '&query=true&search=true&searchtype=BasicSearch&search_field=productname&search_text=pack';
	var SpecialSearch = encodeURI(BasicSearch);
	window.open("index.php?module=Products&action=Popup&html=Popup_picker&form=vtlibPopupView&forfield="+fldname+"&srcmodule="+MODULE+"&forrecord="+ID+SpecialSearch,"vtlibui10","width=680,height=602,resizable=0,scrollbars=0,top=150,left=200");
}
```
2. **insert the javascript file that contains our new function in the HEADERSCRIPT hook to make it available**

 ```php
<?php
include_once('vtlib/Vtiger/Module.php');
$mod_acc = Vtiger_Module::getInstance('Accounts');
$mod_acc->addLink('HEADERSCRIPT', 'ProductAssetCapture', 'modules/Assets/assetcapture.js');
?>
```
3. **register the function for the capture field in the module that appears in the popup**

 ```php 
diff --git a/modules/Products/Products.php b/modules/Products/Products.php
index cf4764d..70a7d83 100755
--- a/modules/Products/Products.php
+++ b/modules/Products/Products.php
@@ -87,6 +87,14 @@ class Products extends CRMEntity {
 		$this->log->debug("Exiting Product method ...");
 	}
+	function getvtlib_open_popup_window_function($fieldname,$basemodule) {
+		if ($fieldname=='product' and $basemodule=='Assets') {
+			return 'productCaptureOnAssets';
+		} else {
+			return 'vtlib_open_popup_window';
+		}
+	}
+
 	function save_module($module)
 	{
 		//Inserting into product_taxrel table
```
### Example: advanced search
This example will modify the product capture field on Assets, so it lists only those products that contain the text "Pack" or are in the "Hardware" category.

 1. **define the new javascript function that will be called**
 
 Create the script modules/Assets/assetcapture.js (it could be anywhere really)

 ```php 
function productCaptureOnAssets(fromlink,fldname,MODULE,ID) {
	var searchConditions = [
		{"groupid":"1",
		 "columnname":"vtiger_products:productname:productname:Products_Product_Name:V",
		 "comparator":"c",
		 "value":"pack",
		 "columncondition":"or"},
		{"groupid":"1",
		 "columnname":"vtiger_products:productcategory:productcategory:Products_Product_Category:V",
		 "comparator":"e",
		 "value":"Hardware",
		 "columncondition":""}
	];
	var advSearch = '&query=true&searchtype=advance&advft_criteria='+convertArrayOfJsonObjectsToString(searchConditions);
	var SpecialSearch = encodeURI(advSearch);
	window.open("index.php?module=Products&action=Popup&html=Popup_picker&form=vtlibPopupView&forfield="+fldname+"&srcmodule="+MODULE+"&forrecord="+ID+SpecialSearch,"vtlibui10","width=680,height=602,resizable=0,scrollbars=0,top=150,left=200");
}
```
 <div class="notices blue">
The <strong> convertArrayOfJsonObjectsToString()</strong> function is a utility function given by coreBOS. It is defined in include/js/vtlib.js. You can use your own or encode the array of json objects as you see fit.</div>


 <div class="notices yellow">
To get the array of JSON conditions in the above script I created a filter on the products module with these exact conditions, I saved it and coreBOS created the array for me and sent it in to be saved. I captured it using the browser and just had to copy it into my code.
</div>

 ![](advancedsearchcriteriafromfilter02.png?width=100%)


 2. **insert the javascript file that contains our new function in the HEADERSCRIPT hook to make it available**

 ```php
<?php
include_once('vtlib/Vtiger/Module.php');
$mod_acc = Vtiger_Module::getInstance('Accounts');
$mod_acc->addLink('HEADERSCRIPT', 'ProductAssetCapture', 'modules/Assets/assetcapture.js');
?>
```
 3. **register the function for the capture field in the module that appears in the popup**

 ```php
diff --git a/modules/Products/Products.php b/modules/Products/Products.php
index cf4764d..70a7d83 100755
--- a/modules/Products/Products.php
+++ b/modules/Products/Products.php
@@ -87,6 +87,14 @@ class Products extends CRMEntity {
 		$this->log->debug("Exiting Product method ...");
 	}
+	function getvtlib_open_popup_window_function($fieldname,$basemodule) {
+		if ($fieldname=='product' and $basemodule=='Assets') {
+			return 'productCaptureOnAssets';
+		} else {
+			return 'vtlib_open_popup_window';
+		}
+	}
+
 	function save_module($module)
 	{
 		//Inserting into product_taxrel table
```

### Example: CODE

 [Here is the code above with the patch for products.](productcaptureonassets.zip)

### Warnings 

 <div class="notices red"> When a uitype10 field has more than one module to select from the FIRST module in the options list will be called to get the name of the custom function. Since the order of the modules can be changed/established in the database you MUST implement the getvtlib_open_popup_window_function() function in ALL the possible modules or make sure you remember to change the function to the first module if you change the order (which is much harder because you most probably won't remember).

 <br>
 </br>
 <strong> As of November 2016 </strong>
 </div> 
