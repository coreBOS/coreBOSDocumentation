---
title: 'List Columns'
metadata:
    description: 'The purpose of this mapping is to override the predefined columns that appear on the related and popup lists for a module.'
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
        - adminmanuals
        - businessmappings
    tag:
        - listcolumns
---

The purpose of this mapping is to override the predefined columns that appear on the related and popup lists for a module. Each module has two hard coded lists of columns, one defines the columns that are showed when the module is on a related lists (list_fields) and the other defines the columns that are shown in the module's popup capture screen (search_fields). Many times we want to be able to change these columns because the default ones aren't important for us or some users need more information in the popup screen. Using the List Columns mapping you can adapt these lists to your requirements without modifying the code.

The accepted format is:

```xml
<map>
<originmodule>
<originid>22</originid>  {optional}
<originname>{ModuleName}</originname>
</originmodule>
<relatedlists>
<relatedlist>
<module>{parentmodule}</module>
<linkfield></linkfield>
<columns>
    <field>
    <label></label>
    <name></name>
    <table></table>  {optional}
    <columnname></columnname>  {optional}
    </field>
    ...
</columns>
</relatedlist>
....
</relatedlists>
<popup>
<linkfield></linkfield>
<columns>
    <field>
    <label></label>
    <name></name>
    <table></table>  {optional}
    <columnname></columnname>  {optional}
    </field>
    ...
</columns>
</popup>
</map>
```
where we can define a different set of columns per related lists and one for the popup screen.

The name of the mapping must be **{ModuleName}_ListColumns** and the name of the global variable, if you need it to be per user, would be: **BusinessMapping_{ModuleName}_ListColumns**

The way to understand this map is like this:

<div class="notices blue">
this Potentials_ListColumns map is for Potentials lists, when you show a list of potential records, in the Contacts module I want you to show these columns, when you show that list in Accounts I want you to show these others,... when you open a popup to select a potential record I want you to show these fields. So, all the field references must be fields that are on the Potentials.
</div>

<div class="notices blue">
If you want to change how contacts appear in their lists then you have to create a Contacts_ListColumns and open a related list section for Potentials
</div>

<div class="notices blue">
If you need to modify the columns that appear in the Global Search for the module, create a section where parentmodule is set to Utilities.
</div>

<br>

## Popup Query Conditions

This feature helps us filter the records that appear in the popup screen. Before we had these conditions we had to code the change using the [Popup Query Hook](../../../10.developer-guide/03.architecture-concepts/77.popup_query_hook). Now the job can be done by adding a simple map in the **cbMap** module.

Below you can see an example of the map in the **Products** module:

```xml
<map>
<originmodule>
    <originname>Products</originname>
</originmodule>
<popup>
    <linkfield>productcode</linkfield>
    <columns>
        <field>
            <name>productcode</name>
        </field>
        <field>
            <name>productname</name>
        </field>
        <field>
            <name>unit_price</name>
        </field>
    </columns>
<conditions>
    <condition>
        <forfield>productid</forfield>
        <value>[{"fieldname":"unit_price","operation":"less than","value":"5","valuetype":"rawtext","joincondition":"and","groupid":"0","groupjoin":""}]</value>
    </condition>
</conditions>
</popup>
</map>
```

In the `originmodule` we have to specify, as we mentioned above, the target module, which in our case is **Products**. 
Between the `linkfield` tags we specify a field name from **Products** we want to refer to and enter the module after we click it. To continue with the `field` tags we have to enter the desired set of fields that will appear in the popup screen. After we must include the `conditions`, where initialy we select the related field (uitype 10) between the `forfield` tags, which is in every module related to **Products**. So, for example if you enter the **InventoryDetails** module and try to link a specific product, in the popup screen are going to be shown only the records that satisfy the conditions set between the `value` tags.

> [{"fieldname":"unit_price","operation":"less than","value":"5","valuetype":"rawtext","joincondition":"and","groupid":"0","groupjoin":""}].

Basically in this example we tell the system that we want only records which, for the *unit_price* field, the value is **less than** 5.

In response we will get the products which unit price is smaller than 5.


> **_Last tip:_**  If you need an easy way to write the condition you can check the **cbQuestion** module, enter the *Builder* mode and make specific conditions which are going to be reflected as a line of code coming to your help. Access this link in your coreBOS installation: `index.php?action=Builder&module=cbQuestion`

------------------------------------------------------------------------

[Next](../23.record_set/item.md) | Chapter 7: Record Set Mapping.

------------------------------------------------------------------------