---
title: 'Popup Filter'
metadata:
    description: 'The purpose of this mapping is to filter in the popup window by comparing fields from that module to a certain value or to another field from modules by navigating through infinite link fields when the relations exist.'
    author: 'Enea Dudija'
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
        - popupfilter
---

This new map helps us filter records in the popup window.
So, when we open the popup from an uitype10 field now we are able to see records that satisfy conditions we set on the map. 
The advantage of this method is that we can compare a field with another one by accessing an infinite number of uitype10s, hence if we want to take a value from a field in a third or more relation, easily we can navigate through link fields between modules as long as there exists a relation.
Below there is an example of a map built for **AssetDetails** module in order to filter **ProductComponents** where **_frompdo_** is equal to the **_product_** in **_related_assets_** of the **AssetDetail**. 

In a few words we are in the **AssetDetails** module, go to **$related_assets** which is the relation field to the **Assets** module and from there we take this **$product field**: 


```xml
<map>
        <modulename>AssetDetails</modulename> {module where we open the popup}

        <field>
            <fieldname>related_productcomponent</fieldname> {the uitype10 field where we click to open the popup}

            <modulename>ProductComponent</modulename>  {the module that appears in the popup}
            <advft_criteria>[{"groupid":1,"columnname":"frompdo","comparator":"e","value":"$related_assets.$product","columncondition":""}]</advft_criteria>
            <advft_criteria_groups>[]</advft_criteria_groups>
        </field>

{after “columnname:” we specify a field from the module where we are trying to filter, ProductComponent in our case; meanwhile as value we specify the field that we want to compare with. We can navigate through uitype10 using ‘.’ to separate fields and the ‘$’ sign before names}

  <field>
            <fieldname>related_ad_servicecontact</fieldname>
            <modulename>ServiceContracts</modulename>
            <advft_criteria>[{"groupid":1,"columnname":"sc_related_to","comparator":"e","value":"$related_assets.$account","columncondition":""}]</advft_criteria>
            <advft_criteria_groups>[]</advft_criteria_groups>
        </field>
    </map>
```

The map name must always be **{Module name}_PopupFilter**. 
The type of map: **Popup Filter**
In red color there are hints of how to construct the map. We can add <field> </field> tags to specify a new filter for another uitype10 of that module. 
