---
title: 'Field Set Mapping'
metadata:
    description: 'This map defines a heterogeneous set of fields that belong to some modules.'
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
        - fieldset
---
---

The purpose of this mapping is to define a heterogeneous set of fields
that belong to some modules. Simply a bunch of fields. This could be
used to define a set of fields to launch a mass operation upon or a set
of fields which must be excluded/included from some global process.

The accepted format is:
```xml
     <map>
      <module>
      <name>ModuleName</name>
      <fields>
        <field>
          <name>fieldname</name>
          <info>anything you need</info>
        </field>
      .....
      </fields>
      </module>
      ....
     </map>
```
You will be able to get the set of fields using the getFieldSet()
method, and the fields on one module with the getFieldSetModule($module)
method.


<br>
------------------------------------------------------------------------

[Next](../19.masterdetailmapping) | Chapter 10: Master Detail Mapping.

------------------------------------------------------------------------