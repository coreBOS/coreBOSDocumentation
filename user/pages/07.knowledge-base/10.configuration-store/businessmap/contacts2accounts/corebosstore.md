---
title: 'Contacts to Accounts'
metadata:
    description: 'Business Map to convert Contacts to Accounts'
    author: 'JPL TSolucio, S.L.'
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
        - businessmappings
        - configuration
    tag:
        - fieldmapping
---

Business Map to convert Contacts to Accounts

===

```xml
<map>
  <originmodule>
    <originname>Contacts</originname>
  </originmodule>
  <targetmodule>
    <targetname>Accounts</targetname>
  </targetmodule>
<fields>
  <field>
    <fieldname>accountname</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>firstname</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
      <Orgfield>
        <OrgfieldName>lastname</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
      <delimiter> </delimiter>
    </Orgfields>
  </field>
  <field>
  <fieldname>accounttype</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>Customer</OrgfieldName>
        <OrgfieldID>CONST</OrgfieldID>
      </Orgfield>
    </Orgfields>
  </field>
  <field>
  <fieldname>phone</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>phone</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
    </Orgfields>
  </field>
  <field>
  <fieldname>fax</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>fax</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
    </Orgfields>
  </field>
  <field>
  <fieldname>otherphone</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>otherphone</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
    </Orgfields>
  </field>
  <field>
  <fieldname>email1</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>email</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
    </Orgfields>
  </field>
  <field>
  <fieldname>email2</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>secondaryemail</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
    </Orgfields>
  </field>
  <field>
  <fieldname>emailoptout</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>emailoptout</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
    </Orgfields>
  </field>
  <field>
  <fieldname>notify_owner</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>notify_owner</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
    </Orgfields>
  </field>
  <field>
  <fieldname>bill_street</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>mailingstreet</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
    </Orgfields>
  </field>
  <field>
  <fieldname>bill_city</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>mailingcity</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
    </Orgfields>
  </field>
  <field>
  <fieldname>bill_state</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>mailingstate</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
    </Orgfields>
  </field>
  <field>
  <fieldname>bill_code</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>mailingzip</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
    </Orgfields>
  </field>
  <field>
  <fieldname>bill_country</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>mailingcountry</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
    </Orgfields>
  </field>
  <field>
  <fieldname>bill_pobox</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>mailingpobox</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
    </Orgfields>
  </field>
  <field>
  <fieldname>ship_street</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>otherstreet</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
    </Orgfields>
  </field>
  <field>
  <fieldname>ship_city</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>othercity</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
    </Orgfields>
  </field>
  <field>
  <fieldname>ship_state</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>otherstate</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
    </Orgfields>
  </field>
  <field>
  <fieldname>ship_code</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>otherzip</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
    </Orgfields>
  </field>
  <field>
  <fieldname>ship_country</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>othercountry</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
    </Orgfields>
  </field>
  <field>
  <fieldname>ship_pobox</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>otherpobox</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
    </Orgfields>
  </field>
  <field>
  <fieldname>description</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>description</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
    </Orgfields>
  </field>
  <field>
  <fieldname>converted_from</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>record_id</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
    </Orgfields>
  </field>
</fields>
<!--
	// Left out from Account
	website
	tickersymbol
	parentid
	employees
	ownership
	rating
	industry
	siccode
	annualrevenue
 
	// Left out from Contact
	salutation
	accountid
	homephone
	leadsource
	mobile
	title
	department
	birthday
	reportsto
	assistant
	assistantphone
	donotcall
	reference
	portal
	support_start_date
	support_end_date
	imagename
-->
</map>
```

This script will add the "converted from" field present in the mapping and the action link on Contacts.

```php
<?php
// Turn on debugging level
$Vtiger_Utils_Log = true;
 
include_once('vtlib/Vtiger/Module.php');
 
$module = Vtiger_Module::getInstance('Accounts');
 
if($module) {
    $blockInstance = VTiger_Block::getInstance('LBL_ACCOUNT_INFORMATION',$module);
 
	if($blockInstance) {
 
		$field = new Vtiger_Field();
		$field->name = 'converted_from';
		$field->label= 'Converted From';
		$field->table = $module->basetable;
		$field->column = 'converted_from';
		$field->columntype = 'INT(11)';
		$field->uitype = 10;
		$field->displaytype = 1;
		$field->typeofdata = 'I~O';
		$field->presence = 0;
		$blockInstance->addField($field);
		$field->setRelatedModules(Array('Contacts'));
 
		echo "<br><b>Added Field to ".$module->name." module.</b><br>";
 
	} else {
		echo "<b>Failed to find ".$module->name." block</b><br>";
	}
 
} else {
	echo "<b>Failed to find ".$module->name." module.</b><br>";
}
 
$module = Vtiger_Module::getInstance('Contacts');
 
if($module) {
 
	$module->addLink('DETAILVIEWBASIC','Convert to Account','index.php?module=Accounts&action=EditView&cbfromid=$RECORD$');
 
} else {
	echo "<b>Failed to find ".$module->name." module.</b><br>";
}
?>
```

<br>
------------------------------------------------------------------------

[Next](../helpdesk2salesorder) | Chapter 3: HelpDesk2SalesOrder.

------------------------------------------------------------------------