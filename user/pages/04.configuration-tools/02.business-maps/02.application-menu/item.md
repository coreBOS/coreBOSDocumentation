---
title: 'Application Menu'
content:
    items:
        - '@self.children'
    limit: 5
    order:
        by: date
        dir: desc
    pagination: true
    url_taxonomy_filters: true
---

Application Menu
================

The purpose of this mapping is to return the JSON layout of the given
menu which is defined inside coreBOS. This is normally used to export a
menu layout to external applications. This way we can use coreBOS menu
editor to define the menus we want and use Global Variables to apply an
escalation to return different menus to different users.

The accepted format is:
```xml
    <map>
      <menuname>my_useful_menu</menuname> 
    </map>
```