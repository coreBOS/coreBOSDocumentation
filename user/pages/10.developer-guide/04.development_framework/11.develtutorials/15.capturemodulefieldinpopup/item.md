---
title: 'How to fill in additional fields when selecting a record in a popup screen'
metadata:
    description: 'How to fill in additional fields when selecting a record in a popup screen'
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
        - popup
    tag:
        - howto
        - capture
---

<div class="notices red">This article is obsolete! As of December 2014 we have a hook to make this easy without the need of modifying any base application code.</div>

[Read all about it on the Hooks wiki page!](../20.corebos_hooks).


In vtiger CRM 5.x and coreBOS code prior to December 2014, this task is still cumbersome and requires code modifications.

This page describes the process by documenting the answer given by
srhtech in the vtiger CRM forum thread [Quote information mapping when adding organization](https://discussions.vtiger.com//discussion/172541/quote-information-mapping-when-adding-orginzation).

You have to edit *include/utils/ListViewUtils.php* which is in charge of
creating the list so the links have more information, then you have to
modify the javascript to use those new fields and fill in the fields.
That is in the modules' javascript file.

I went to the *include/utils/ListViewUtils.php* file and edited the following between 1957 and 2017

```php
elseif ($popuptype == "specific_account_address") {
require_once('modules/Accounts/Accounts.php');
$acct_focus = new Accounts();
$acct_focus->retrieve_entity_info($entity_id, "Accounts");
$slashes_temp_val = popup_from_html($temp_val);
$slashes_temp_val = htmlspecialchars($slashes_temp_val, ENT_QUOTES, $default_charset);
$xyz = array('bill_street', 'bill_city', 'bill_code', 'bill_pobox', 'bill_country', 'bill_state', 'ship_street', 'ship_city', 'ship_code', 'ship_pobox', 'ship_country', 'ship_state', 'cf_709');
for ($i = 0; $i < 12; $i++) {
if (getFieldVisibilityPermission($module, $current_user->id, $xyz[$i]) == '0') {
$acct_focus->column_fields[$xyz[$i]] = $acct_focus->column_fields[$xyz[$i]];
}
else
$acct_focus->column_fields[$xyz[$i]] = '';
}
$bill_street = str_replace(array("\r", "\n"), array('\r', '\n'), popup_decode_html($acct_focus->column_fields['bill_street']));
$ship_street = str_replace(array("\r", "\n"), array('\r', '\n'), popup_decode_html($acct_focus->column_fields['ship_street']));
$count = counterValue();
$value = 'column_fields['bill_city']) . '", "' . popup_decode_html($acct_focus->column_fields['ship_city']) . '", "' . popup_decode_html($acct_focus->column_fields['bill_state']) . '", "' . popup_decode_html($acct_focus->column_fields['ship_state']) . '", "' . popup_decode_html($acct_focus->column_fields['bill_code']) . '", "' . popup_decode_html($acct_focus->column_fields['ship_code']) . '", "' . popup_decode_html($acct_focus->column_fields['bill_country']) . '", "' . popup_decode_html($acct_focus->column_fields['ship_country']) . '","' . popup_decode_html($acct_focus->column_fields['bill_pobox']) . '", "' . popup_decode_html($acct_focus->column_fields['ship_pobox']) . '", "' . popup_decode_html($acct_focus->column_fields['cf_709']) . '");\'id = ' . $count . '>' . textlength_check($temp_val) . '';
}
elseif ($popuptype == "specific_contact_account_address") {
require_once('modules/Accounts/Accounts.php');
$acct_focus = new Accounts();
$acct_focus->retrieve_entity_info($entity_id, "Accounts");

$slashes_temp_val = popup_from_html($temp_val);
$slashes_temp_val = htmlspecialchars($slashes_temp_val, ENT_QUOTES, $default_charset);

$bill_street = str_replace(array("\r", "\n"), array('\r', '\n'), popup_decode_html($acct_focus->column_fields['bill_street']));
$ship_street = str_replace(array("\r", "\n"), array('\r', '\n'), popup_decode_html($acct_focus->column_fields['ship_street']));
$count = counterValue();
$value = 'column_fields['bill_city']) . '", "' . popup_decode_html($acct_focus->column_fields['ship_city']) . '", "' . popup_decode_html($acct_focus->column_fields['bill_state']) . '", "' . popup_decode_html($acct_focus->column_fields['ship_state']) . '", "' . popup_decode_html($acct_focus->column_fields['bill_code']) . '", "' . popup_decode_html($acct_focus->column_fields['ship_code']) . '", "' . popup_decode_html($acct_focus->column_fields['bill_country']) . '", "' . popup_decode_html($acct_focus->column_fields['ship_country']) . '","' . popup_decode_html($acct_focus->column_fields['bill_pobox']) . '", "' . popup_decode_html($acct_focus->column_fields['ship_pobox']) . '", "' . popup_decode_html($acct_focus->column_fields['cf_709']) . '");\'id = ' . $count . '>' . textlength_check($temp_val) . '';
} elseif ($popuptype == "specific_potential_account_address") {
$slashes_temp_val = popup_from_html($temp_val);
$slashes_temp_val = htmlspecialchars($slashes_temp_val, ENT_QUOTES, $default_charset);

// For B2C support, Potential was enabled to be linked to Contacts also.
// Hence we need case handling for it.
$relatedid = $adb->query_result($list_result, $list_result_count, "related_to");
$relatedentity = getSalesEntityType($relatedid);
if ($relatedentity == 'Accounts') {
require_once('modules/Accounts/Accounts.php');
$acct_focus = new Accounts();
$acct_focus->retrieve_entity_info($relatedid, "Accounts");
$account_name = getAccountName($relatedid);

$slashes_account_name = popup_from_html($account_name);
$slashes_account_name = htmlspecialchars($slashes_account_name, ENT_QUOTES, $default_charset);

$xyz = array('bill_street', 'bill_city', 'bill_code', 'bill_pobox', 'bill_country', 'bill_state', 'ship_street', 'ship_city', 'ship_code', 'ship_pobox', 'ship_country', 'ship_state', 'cf_709');
for ($i = 0; $i < 12; $i++) {
if (getFieldVisibilityPermission('Accounts', $current_user->id, $xyz[$i]) == '0') {
$acct_focus->column_fields[$xyz[$i]] = $acct_focus->column_fields[$xyz[$i]];
}
else
$acct_focus->column_fields[$xyz[$i]] = '';
}
$bill_street = str_replace(array("\r", "\n"), array('\r', '\n'), popup_decode_html($acct_focus->column_fields['bill_street']));
$ship_street = str_replace(array("\r", "\n"), array('\r', '\n'), popup_decode_html($acct_focus->column_fields['ship_street']));
$count = counterValue();
$value = 'column_fields['bill_city']) . '", "' . popup_decode_html($acct_focus->column_fields['ship_city']) . '", "' . popup_decode_html($acct_focus->column_fields['bill_state']) . '", "' . popup_decode_html($acct_focus->column_fields['ship_state']) . '", "' . popup_decode_html($acct_focus->column_fields['bill_code']) . '", "' . popup_decode_html($acct_focus->column_fields['ship_code']) . '", "' . popup_decode_html($acct_focus->column_fields['bill_country']) . '", "' . popup_decode_html($acct_focus->column_fields['ship_country']) . '","' . popup_decode_html($acct_focus->column_fields['bill_pobox']) . '", "' . popup_decode_html($acct_focus->column_fields['ship_pobox']) . '", "' . popup_decode_html($acct_focus->column_fields['cf_709']) . '");\'id = ' . $count . '>' . textlength_check($temp_val) . '';
```
The basics of all that was to edit
```
$xyz = array('bill_street', 'bill_city', 'bill_code', 'bill_pobox', 'bill_country', 'bill_state', 'ship_street', 'ship_city', 'ship_code', 'ship_pobox', 'ship_country', 'ship_state', 'cf_709');
```
to include the custom field, and then add
```
 , "' . popup_decode_html($acct_focus->column_fields['cf_709']) . '"
```

to send the data to the javascript function.

Then I edited the *modules/Accounts/Accounts.js* and added the following at line 103

```
if(typeof(window.opener.document.EditView.cf_821) != 'undefined')
window.opener.document.EditView.cf_821.value = cf_709;
```

**Thank you srhtech !!**
