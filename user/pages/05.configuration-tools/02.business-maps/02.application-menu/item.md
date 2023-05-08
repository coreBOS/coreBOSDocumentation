---
title: 'Application Menu Business Mapping'
metadata:
    description: 'Access any saved menu structure using this business map.'
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
        - businessmappings
        - adminmanual
    tag:
        - application
        - menu
---

The purpose of the coreBOS Menu Layout Mapping is to retrieve and export the JSON layout of a specified menu from the coreBOS application. This feature allows you to define menus within coreBOS using the menu editor and then export them for use in external applications. By leveraging global variables, you can dynamically apply different menus to different users based on predefined conditions.

===

The accepted format for the mapping is as follows:

```xml
<map>
    <menuname>my_useful_menu</menuname> 
</map>
```

To retrieve the menu dynamically by passing the menu name as a parameter, you can use the special menuname value `get_name_from_menuname_parameter` in the mapping:

```xml
<map>
    <menuname>get_name_from_menuname_parameter</menuname> 
</map>
```

For example, if you have named your business map as `GenericMenuAccess`, you can use the following PHP code to retrieve a saved menu named `SomeSavedMenuName`:

```php
$mapid = 'convert GenericMenuAccess to a crmid';
$map = new cbMap();
$map->id = $mapid;
$map->retrieve_entity_info($mapid, 'cbMap');
$mapinfo = $map->ApplicationMenu(['menuname' => 'SomeSavedMenuName']);
```

If you prefer to use the coreBOS web service development tool, you can use the following code:

```php
$params = array(
	'sessionName' => $cbSessionID,
	'operation' => 'ProcessMap',
	'mapid' => 'GenericMenuAccess',
	'parameters' => '{"menuname":"SomeSavedMenuName"}',
);
$response = $httpc->doPost($params, false);
$dmsg.= debugmsg('Webservice response', $response);
var_dump($response);
```

These examples demonstrate how to retrieve and utilize the coreBOS menu layout mapping to export menus for external applications or integrate them into your custom development projects.

<br>
------------------------------------------------------------------------

[Next](../16.kanban) | Chapter 23: Kanban View.

------------------------------------------------------------------------