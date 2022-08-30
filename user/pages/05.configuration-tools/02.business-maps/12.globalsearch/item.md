---
title: 'Global Search Autocomplete Mapping'
metadata:
    description: 'This map defines the set of modules and fields you want to launch a reduced global search on.'
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
        - globalsearch
---
---

This business map is really a configuration setting. Most business maps
are generic, whereas you can use them on many modules or for various
purposes. This mapping is, specifically, to define the set of modules
and fields you want to launch a reduced global search on.

As of the creation and implementation of this map, if it exists, you
will be able to start writing in the global search text box to get an
autocomplete dropdown with values that it finds in the modules and
fields defined in the mapping.
```xml
    <map>
      <mincharstosearch>3</mincharstosearch>
      <maxresults>10</maxresults>
      <searchin>
        <module>
          <name>Potentials</name>
          <searchfields>field1,field2,...,fieldn</searchfields>
          <searchcondition>startswith|contains</searchcondition>
          <showfields>field1,field2,...,fieldn</showfields>
        </module>
       ...
      </searchin>
    </map>
```
As usual, the mere existence of the mapping with the name
**GlobalSearchAutocomplete** will activate the functionality and, as
with all business maps you can define it using the global variable
**BusinessMap\_GlobalSearchAutocomplete** to apply it only to certain
users.

This feature was implemented by
[Albana](https://github.com/AlbanaCelepija): Thank you!!

This is the map I used to test it:
```xml
    <map>
      <mincharstosearch>2</mincharstosearch>
      <maxresults>10</maxresults>
      <searchin>
        <module>
          <name>Potentials</name>
          <searchfields>potentialname,sales_stage,amount</searchfields>
          <searchcondition>startswith</searchcondition>
          <showfields>potentialname,sales_stage,amount,forecast_amount</showfields>
        </module>
        <module>
          <name>Accounts</name>
          <searchfields>accountname,industry,employees</searchfields>
          <searchcondition>startswith</searchcondition>
          <showfields>accountname,industry,employees,email1</showfields>
        </module>
      </searchin>
    </map>
```

<br>
------------------------------------------------------------------------

[Next](../07.detailviewlayout) | Chapter 19: Detail View Layout.

------------------------------------------------------------------------