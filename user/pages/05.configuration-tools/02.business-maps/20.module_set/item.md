---
title: 'Module Set Mapping'
metadata:
    description: 'This map defines a heterogeneous set of module names. Simply a bunch of modules.'
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
        - moduleset
---
---

The purpose of this mapping is to define a heterogeneous set of module
names. Simply a bunch of modules. This could be used to define a set of
modules to launch a mass operation upon or a set of modules that must be
excluded from some global process.

The accepted format is:
```xml
    <map>
      <modules>
        <module>ModuleName</module>
        <module>ModuleName2</module>
        ...
      </modules> 
    </map>
```
You will be able to get the set of modules using the getFullModuleSet()
method.


<br>
------------------------------------------------------------------------

[Next](http://localhost/coreBOSDocumentation/configuration-tools/business-maps/field_set) | Chapter 9: Field Set Mapping.

------------------------------------------------------------------------