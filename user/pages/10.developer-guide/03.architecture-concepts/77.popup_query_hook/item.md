---
title: 'Popup query hook'
metadata:
    description: 'This hook permits us to directly manipulate the query to be executed in the Pop-up capture screen for our module.'
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

This hook permits us to directly manipulate the query to be executed in the Pop-up capture screen for our module.

===

Although the Pop-up capture screen has some very advanced searching capabilities that can be directly used through [pop-up open hook as can be read here.](../76.popup_open_hook)
 That hook grows on coreBOS search system which is limited to fields directly on the module being searched, so we can restrict the list of records shown based on any combination of fields directly ON the module, but we can not limit it by fields on some other related module. That is where this hook comes into play.

The rest of the article will be based on a real example of an open source module that coreBOS has which uses this hook to implement the pop-up restrictions it requires without modifying any of the base code in the application. The module is [coreBOS Address,](https://github.com/tsolucio/coreBOSAddress) which represents a many to many relation between physical addresses and accounts/contacts. Any given address record can be related to many accounts and contacts while any given account or contact can have many addresses. You can [find the module on github.](https://github.com/tsolucio/coreBOSAddress) 

This module adds some "helper" fields on the inventory modules so you can easily select any address related to the account/contact of the record. For example, when creating an invoice, you select an account and the billing and shipping address fields get automatically filled in. Now imagine that the invoice we are creating requires us to have a different billing or shipping address. Obviously, we want to select this address from among the different addresses that we have already created in the [coreBOS Address module.](https://github.com/tsolucio/coreBOSAddress) To make this possible, that module adds an address select field for us to click on and open a pop-up window with all the addresses, so we can select the one we need and have it update the invoice address fields for us.

The issue is that to make this even more useful than it already is, we want the pop-up window with the addresses to show us ONLY those addresses that are related to the account and/or contact selected on the invoice. After all, those are the ones with higher probability of being the one we want.

If the account/contact field were directly on the address record we could use the [pop-up open hook](../76.popup_open_hook) to add a search condition on the field(s), but the relation between account/contact and address is many to many, the relation is not reflected directly on the records of the address module but in another intermediate database table, so we need something more. That is where the **pop-up query hook** comes into play.

To use this hook we add a method to our module called **getQueryByModuleField().** The pop-up capture screen code will detect this method and call it right before launching the query that it has constructed. If the method returns a query, the code will understand that the query coming from this method is better than the one it has obtained and will use it instead of it's own.

It is that easy, simply add a method and return the SQL you want the pop-up to execute. In that SQL we can establish any joins we need to reach related information and restrict the set of records returned as needed.

The profile of the method is like this:

```php
function getQueryByModuleField(sourcmodule, forfield, forrecord, query) {
```
where
- **sourcemodule:** is a string representing the module where the field opening the pop-up is. In the case of the example above it would contain Invoice
- **forfield:** is a string representing the name of the field opening the pop-up.
- **forrecord:** is a number representing the crmid of the record being edited. It will be empty if we are creating.
- **query:** is a string representing the full SQL query that the pop-up capture code has obtained. 

These four parameters should be all we need to decide what query we need to return, although it would have been nice to get the query in it's individual parts.

Let's have a look at how the [coreBOS Address module](https://github.com/tsolucio/coreBOSAddress) handles this to restrict the set of address records shown to those of the account and/or contact selected on the invoice.

First it adds a [pop-up open hook](../76.popup_open_hook) in order to capture the accountID and the contactID selected on the invoice and pass them to the pop-up capture code in the URL opening the window. This is similar to adding search conditions, the only difference being that in this case we pass in two variables that the pop-up capture code does not use, they are intended for our custom query method. [This looks like this:](https://github.com/tsolucio/coreBOSAddress/blob/master/modules/cbAddress/cbAddress.js#L25)

```php 
function cbAddressOpenCapture(fromlink,fldname,MODULE,ID) {
	var WindowSettings = "width=680,height=602,resizable=0,scrollbars=0,top=150,left=200";
	var baseURL = "index.php?module=cbAddress&action=Popup&html=Popup_picker&form=vtlibPopupView&forfield="+fldname+"&srcmodule="+MODULE;
	if (MODULE != 'PurchaseOrder')
		var accountid = document.getElementsByName("account_id")[0].value;
	if (MODULE != 'Accounts')
		var contactid = document.getElementsByName("contact_id")[0].value;
	switch (MODULE) {
		case 'Accounts':
			window.open(baseURL+"&forrecord="+ID+"&acc_id="+ID+"&cbcustompopupinfo=acc_id","vtlibui10",WindowSettings);
		break;
		case 'Contacts':
			window.open(baseURL+"&forrecord="+ID+"&acc_id="+accountid+"&cont_id="+contactid+"&cbcustompopupinfo=acc_id;cont_id","vtlibui10",WindowSettings);
		break;
		case 'SalesOrder':
		case 'Invoice':
			window.open(baseURL+"&cont_id="+contactid+"&acc_id="+accountid+"&relmod_id="+accountid+"&cbcustompopupinfo=acc_id;cont_id;relmod_id","vtlibui10",WindowSettings);
		break;
		case 'Quotes':
			window.open(baseURL+"&forrecord="+ID+"&acc_id="+accountid+"&cont_id="+contactid+"&relmod_id="+accountid+"&cbcustompopupinfo=acc_id;cont_id;relmod_id","vtlibui10",WindowSettings);
		break;
		case 'PurchaseOrder':
			window.open(baseURL+"&forrecord="+ID+"&cont_id="+contactid+"&relmod_id="+contactid+"&cbcustompopupinfo=cont_id;relmod_id","vtlibui10",WindowSettings);
		break;
	}
}
```
<div class="notices red">
<strong>!! NOTE: VERY IMPORTANT !! </strong>
In the above code there is an extremely important part that could be bypassed easily. It is the additional parameter <strong>cbcustompopupinfo.</strong> When we use this type of customization instead of the system  

[pop-up open hook](../76.popup_open_hook) we are artificially sending our own custom parameters to the application. In this case the acc_id, cont_id and relmod_id parameters. Since these parameters are totally unknown to the application they are not passed along to any subsequent request made by the popup screen. Normally there won't be any other requests as the set of records returned will fit on one popup screen and the user will simply select the right one, but if the popup screen has a few pages of records and the user goes to another page, launches a search or simply decides to sort them by some field, our custom parameters WILL NOT be sent and the query will fail because it expects these values. In order to inform the application that these values must be respected we have to add the <strong>cbcustompopupinfo</strong> parameter with a semi-colon separated list of the variable names we need to have sent around.

<a href=https://github.com/omarllorens>Thank you Omar.</a>
</div>

Second it adds the <strong>getQueryByModuleField()</strong> method [which looks like this:](https://github.com/tsolucio/coreBOSAddress/blob/master/modules/cbAddress/cbAddress.php#L138)

```php
	function getQueryByModuleField($module, $fieldname, $srcrecord, $query='') {
		// $srcrecord could be empty
		global $adb,$log;
		$query_relation = ' INNER JOIN vtiger_crmentityrel ON (vtiger_crmentityrel.relcrmid = vtiger_crmentity.crmid OR vtiger_crmentityrel.crmid = vtiger_crmentity.crmid) ';
		$wherepos = stripos($query, 'where'); // there is always a where
		$query_body = substr($query, 0, $wherepos-1);
		$query_cond = substr($query, $wherepos+5);
		if($module == 'Invoice' || $module == 'Contacts' || $module == 'Quotes' || $module == 'SalesOrder') {
			$accountID = vtlib_purify($_REQUEST['acc_id']);
			$contactID = vtlib_purify($_REQUEST['cont_id']);
			/*$query = "SELECT vtiger_crmentity.*, vtiger_cbaddress.*, vtiger_cbaddresscf.* 
			FROM vtiger_cbaddress 
			INNER JOIN vtiger_crmentity ON vtiger_crmentity.crmid = vtiger_cbaddress.cbaddressid  
			INNER JOIN vtiger_cbaddresscf ON vtiger_cbaddresscf.cbaddressid = vtiger_cbaddress.cbaddressid 
			LEFT JOIN vtiger_users ON vtiger_users.id = vtiger_crmentity.smownerid 
			LEFT JOIN vtiger_groups ON vtiger_groups.groupid = vtiger_crmentity.smownerid 
			WHERE vtiger_cbaddress.cbaddressid > 0 AND vtiger_crmentity.deleted = 0" ORDER BY cbaddressno ASC ;*/
			if(isset($_REQUEST['cont_id']) && $_REQUEST['cont_id'] !='' && $_REQUEST['acc_id'] =='') {
				$query1 = $query_body . $query_relation . " WHERE (vtiger_crmentityrel.crmid = $contactID OR vtiger_crmentityrel.relcrmid = $contactID) and " . $query_cond;
				return $query1;
			}
			elseif((isset($_REQUEST['acc_id']) && $_REQUEST['acc_id'] !='' && $_REQUEST['cont_id'] =='' )) {
				$query1 = $query_body . $query_relation . " WHERE (vtiger_crmentityrel.crmid = $accountID OR vtiger_crmentityrel.relcrmid = $accountID) and " . $query_cond;
				return $query1;
			}
			elseif(isset($_REQUEST['acc_id']) && $_REQUEST['acc_id'] !='' && isset($_REQUEST['cont_id']) && $_REQUEST['cont_id'] !=''){
				$query1 = $query_body . $query_relation . " WHERE (vtiger_crmentityrel.crmid = $accountID OR vtiger_crmentityrel.relcrmid = $accountID or vtiger_crmentityrel.crmid = $contactID OR vtiger_crmentityrel.relcrmid = $contactID) and " . $query_cond;
				$res = $adb->query($query1);
				$number= $adb->num_rows($res);
				if($number > 0){
					 return $query1;
				}
				else return $query;
			}
			else return $query;
		}
		elseif($module == 'Accounts'){
			$accountID = vtlib_purify($_REQUEST['acc_id']);
			if((isset($_REQUEST['acc_id']) && $_REQUEST['acc_id'] !='')){
				$query1 = $query_body . $query_relation . " WHERE (vtiger_crmentityrel.crmid = $accountID OR vtiger_crmentityrel.relcrmid = $accountID) and " . $query_cond;;
				return $query1;
			}
			else return $query;
		}
		elseif($module == 'PurchaseOrder'){
			$contactID = vtlib_purify($_REQUEST['cont_id']);
			if((isset($_REQUEST['cont_id']) && $_REQUEST['cont_id'] !='')){
				$query1 = $query_body . $query_relation . " WHERE (vtiger_crmentityrel.crmid = $contactID OR vtiger_crmentityrel.relcrmid = $contactID) and " . $query_cond;;
				return $query1;
			}
			else return $query;
		}
		return $query;
	}
```
where we can see that first it looks for the two variables that are intended for this code. If they do not exist then the module is being called from somewhere else that does not require the advanced custom query so it returns the query that the pop-up had already obtained (it could have also returned an empty string or FALSE to obtain the same result). If they do exist then it constructs a personalized SQL query that joins upon the vtiger_crmentityrel table where the many to many relation between account/contact and address is being held and adds the conditions to restrict the set of addresses to those related to the given account or contact. Giving this new SQL back to the pop-up capture code is all that we need to do to have the pop-up filled in with the records we want.

<div class="notices red">
It is important to process the "where" part of the SQL obtained by the pop-up capture code because it will contain search queries that the user may be launching and that should affect the set of records returned.
</div>

In the example above there is some additional code condition to detect the request from the user to show all records. In that case we must return the query obtained by the pop-up capture code and not apply the restrictions.



