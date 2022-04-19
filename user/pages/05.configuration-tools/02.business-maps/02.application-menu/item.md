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

The purpose of this mapping is to return the JSON layout of the given menu which is defined inside coreBOS. This is normally used to export a menu layout to external applications. This way we can use coreBOS menu editor to define the menus we want and use Global Variables to apply an escalation to return different menus to different users.

===

The accepted format is:

```xml
<map>
    <menuname>my_useful_menu</menuname> 
</map>
```

You can use the special menuname `get_name_from_menuname_parameter` to send in the name of the menu you want to retrieve as a parameter to the map. In this case the map is:

```xml
<map>
  <menuname>get_name_from_menuname_parameter</menuname> 
</map>
```

Let's suppose that you named this business map `GenericMenuAccess`, in that case the PHP code to retrieve a saved map named `SomeSavedMenuName` would be

```php
$mapid = 'convert GenericMenuAccess to a crmid';
$map = new cbMap();
$map->id = $mapid;
$map->retrieve_entity_info($mapid, 'cbMap');
$mapinfo = $map->ApplicationMenu(['menuname' => 'SomeSavedMenuName']);
```

and from web service, the coreBOS web service development tool code would be

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

