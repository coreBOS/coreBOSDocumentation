---
title: 'IOMap Business Mapping'
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

IOMap Business Mapping
======================

The accepted format is
```xml
    <map> 
     <input> 
       <fields> 
        <field> 
         <fieldname>recordid</fieldname> 
        </field> 
        <field> 
         <fieldname>originmodule</fieldname> 
        </field> 
       </fields> 
     </input> 
     <output> 
       <fields> 
        <field> 
         <fieldname>targetaction</fieldname> 
        </field> 
       </fields> 
     </output> 
    </map>
```
This type of map is a developer tool. It permits you to define the input
and output parameters of different processes that can be programmed. It
has no visual effect nor functionality inside the application.
