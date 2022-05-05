---
title: 'Configuring Combobox with static values Fields'
metadata:
    description: 'Configuring Combobox with static values Fields.'
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
        - adminmanual
        - businessmappings
    tag:
        - fieldinfo
        - combobox
---

===

This type of functionality applies to normal input fields where the user can type in any text they want but you want to suggest a preferred set of standard/accepted values.

The definition can be [found here](https://www.lightningdesignsystem.com/components/combobox/#Autocomplete-Combobox).

The map looks like this:

```XML
<field>
  <fieldname>potentialname</fieldname>
  <features>
   <feature>
    <name>combobox</name>
    <values>
      <value>value1</value>
      <value>value2</value>
      <value>...</value>
      <value>valueN</value>
    </values>
   </feature>
  </features>
</field>
```
