---
title: 'Importing Data::Special references and comments'
metadata:
    description: 'Product Stock Control'
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
        - import
    tag:
        - reference
        - comments
---

[plugin:youtube](https://youtu.be/41fQCIenRUU)

## Search Reference Fields on (almost) any field of the referenced module

When importing information into the application we can automatically relate the record we are importing with another module when that relationship is direct. For example, if we import a Contact record we can import the Account column with the identifier field of accounts and the new contact will get related correctly.

The CSV contact file shown next will result in a new contact related to the **EDFG Group Limited** account.

```
"Salutation","First Name","Last Name","Office Phone","Organization Name","Mobile"
"","Susan","Wilson","(694) 186-6696","EDFG Group Limited","(838) 935-6869"
```

When the import process reaches the **Organization Name** field, it sees that it is a reference field and automatically searches the Account module for an account with "account name" equal to the value in the import CSV. If found it will relate the two records correctly, if not, a new account will be created and then the relation will be established.

These types of reference fields support an extended syntax whereas you can indicate the module that the value belongs to. This can be seen in the next CSV file:

```
"Salutation","First Name","Last Name","Office Phone","Organization Name","Mobile"
"","Susan","Wilson","(694) 186-6696","Accounts::::EDFG Group Limited","(838) 935-6869"
```

To all effects, this second CSV file will result in the **exact same import process** as the previous one.

This extended functionality is useful when we import a record with a reference field that can point to more than one module. For example, when importing tickets or potentials, where the reference field can point either to an Account or a Contact, so we have to indicate in which module the import process must search for the given value.

The next CSV would be an example of importing opportunity records:

```
"Opportunity Name","Related To","Amount","Type","Expected Close Date"
"EDFG Group Limited - 1000 units","Accounts::::EDFG Group Limited","25000.00","Existing Business","2016-01-07"
"samplevtiger - 1000 units","Contacts::::Susan Wilson","75000.00","--None--","2016-01-03"
```

The field upon which the relation is searched is ALWAYS the identifier field of the module. Every module has a special field called the **entity identifier field**, this special field is the one you can click on inside the application to get to the **detail view** of the record. For example, for Accounts that is the "account name", for potentials the "opportunity name" and for tickets the title or subject of the ticket.

Sometimes we don't have that special field in our import data or, if we do, we can't be sure that the values match exactly. This especially happens when importing to Accounts and Contacts. For these cases, it would be ideal to be able to have the import process search on some other field that we have at hand or that we know is supposed to be unique between the application and the import data.

The ideal/typical scenario is where you have done the **first import right (!)** and added a custom field to the module that indicates the ID of that record in your other system. This is fundamental where you have two system coexisting in the company and you have to do regular imports of information.

**As of coreBOS 5.5** we have extended the extended syntax 8-) so you can indicate the field you want to search upon to find the referenced module. You can now add the field name upon which you want to search AFTER the extended syntax with the same separator "::::". So the next CSV would import potentials searching the first record on the Accounts' siccode field and the second on the Contacts' cf_640 field.

```
"Opportunity Name","Related To","Amount","Type","Expected Close Date"
"Extended Test Account","Accounts::::987654::::siccode","987654","Existing Business","2016-01-07"
"Extended Test Contact","Contacts::::123456::::cf_640","123456","--None--","2016-01-03"
```

[plugin:youtube](https://youtu.be/qKV4DZRiXu0)

## Extended Export Options

There are two global variables that will permit you to define the format that the application should use when exporting reference fields.

By default, the format used will be the module name followed by the module entity name or link field.

Using the **Export_RelatedField_GetValueFrom** global variable you can indicate which field of the module you want to use as the export reference value. So, for example, if you set this variable to **account_no** on the **Accounts** module, when you export Potentials, you will see that the reference field contains the account number and not the account name.

Additionally, you can set the **Export_RelatedField_NameForSearch** global variable to any value in order to have that value appended to the end of the related field export.

Another example. Let's suppose that we want to migrate information from one coreBOS system to another. In the origin application, you have a custom field on your accounts module labeled VATID. This field contains a unique identifier for each Account. The internal name of this field is cf_999. In the second application, this field has been assigned the internal field name cf_888

If we set the **Export_RelatedField_GetValueFrom** global variable to "cf_999" and the **Export_RelatedField_GetValueFrom** global variable to "cf_888" and export potentials from the first system, the "Related to" reference field will read the values of accounts from the "cf_999" field and export a string that looks like this:

```
Accounts::::B99999999::::cf_888
```

which is ready to import correctly into the second application.

## Export Options for Comments

Comments are, to most effects, just another normal module. So you can go to the ModComments module and use all the import and export options there, but, the comments module has a special developer block that permits us to interact with the comments records directly on the module they apply to. This block must be activated defining a [Business Action](../../../05.configuration-tools/03.business-actions).

The comments module has another functionality that permits us to directly export the comments related to a record. You can define a [Business Action](../../../05.configuration-tools/03.business-actions) to add a link (or button) to export the comments like this:

```
Link Type: DETAILVIEWBASIC
Link Label: Export Comments
Link Url: javascript:window.location.href = 'index.php?module=Contacts&action=ContactsAjax&file=ExecuteFunctions&functiontocall=exportUserComments&record=$RECORD$';
Module List: Contacts
```
Obviously, you can adapt that to any module.

![](modcommentsexportaction.png?width=60%)

There is also a [Global Variable](../../../05.configuration-tools/04.global-variables) named **ModComments_Export_Format** that permits us to obtain the export in a spreadsheet format instead of the default CSV.

Finally, the export returns the comment and creation date columns but you can create a [Field Set Business Map](../../../05.configuration-tools/02.business-maps/10.field_set) named **Comments_Export_Columns** to specify the fields you want to export.

```xml
<map>
  <module>
  <name>ModComments</name>
  <fields>
	<field>
	  <name>commentcontent</name>
	</field>
	<field>
	  <name>createdtime</name>
	</field>
	<field>
	  <name>assigned_user_id</name>
	</field>
	<field>
	  <name>related_to</name>
	</field>
  </fields>
  </module>
 </map>
```