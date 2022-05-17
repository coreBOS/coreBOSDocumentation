---
title: 'Record Set Mapping'
metadata:
    description: 'This map defines a heterogeneous set of record IDs. Simply a bunch of CRMIDs of records from different modules.'
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
        - recordset
---
---

The purpose of this mapping is to define a heterogeneous set of record
IDs. Simply a bunch of CRMIDs of records from different modules. This
could be used to define a set of records to launch a mass operation upon
or a set of records that must be excluded from some global process.

In concept, it is very similar to the [Condition Query
Mapping](http://localhost/coreBOSDocumentation/configuration-tools/business-maps/condition-query) where you can
retrieve a set of records from a query. The big difference is that this
mapping easily mixes records from different modules and with no special
condition that the query must fulfill, you just put the IDs, no fuss.

Obviously, the set must be small or will become too complex to maintain.

The accepted format is:
```xml
     <map>
      <records>
      <record>
      <id>1</id> if given, module and value are ignored
      <module>ModuleName</module>
      <value>EntityCustomNumberValue</value> we only search on the uitype 4 field
      <action>include</action>  Include | Exclude | Group  The default action is Exclude
      </record>
      .....
      </records>
      </map>
```
You will be able to ask:

-   for CRMIDs in each action group and module
-   if a given CRMID is in the group
-   get a list of module names that have some CRMIF in the recordset.

<div class="notices blue">
Only IDs that are not DELETED will be
returned.
</div>

<br>
------------------------------------------------------------------------

[Next](http://localhost/coreBOSDocumentation/configuration-tools/business-maps/module_set) | Chapter 8: Module Set Mapping.

------------------------------------------------------------------------