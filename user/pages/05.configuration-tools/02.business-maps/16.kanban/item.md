---
title: 'Kanban View Mapping'
metadata:
    description: 'This map defines a kanban lane view of the records of a module.'
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
        - kanban
---

The purpose of this mapping is to define a kanban lane view of the
records of a module. This map is in the "View Business Map" category as
it serves the purpose of showing the records of a module in a different
way than we usually see them in the list view.

===

With this map, we will be able to divide the records into kanban lanes
based on the distinct values in a field of the module as well as filter
the records based on a search or custom view settings. The kanban view
will permit us to move the records around, effectively changing the
value of the field the lanes are based on as well as get more
information and apply the typical coreBOS actions on each record.

As usual, the map to apply is selected using the name of the map which
must be **{ModuleName}\_Kanban** and you can use the global variable
**BusinessMapping\_{ModuleName}\_Kanban** to define maps based on user
and roles (among other escalation rules) just like most of the other
maps.

The actions supported are:

-   module: Module name to appy the Kanban view
-   lanefield: module field name you want to be showed in kanban lane
    view
-   showsearch: shows the search in kanban view(boolean value)
-   showfilter: shows the filter in kanban view(boolean value)
-   applyfilter: put the filter name you want to apply in kanban view
-   pagesize: number of records to show per lane
-   lanes: here you can customize each lane
-   name: value of module field name to address the changes
-   sequence: the place a lane is going to have in a row
-   library: LDS library name
-   icon: LDS icon name
-   color: CSS color to put to the specific value
-   card: here you can show fields inside a lane's record
-   title: module field name to show as title inside a lane's record
-   field: main field to show inside a record
-   morefields: more fields you can choose to see inside a lane's record

The accepted format is:
```xml
    <map>
        <module>Module name</module>
        <lanefield>Module field name</lanefield>
        <showsearch>0|1</showsearch>
        <showfilter>0|1</showfilter>
        <applyfilter>filter name</applyfilter>
        <pagesize>number of records per lane, by default Application_ListView_PageSize</pagesize>
        <lanes>
          <lane>
            <name>value of module field name</name>
            <sequence></sequence>
            <image>
             <library>LDS library name</library>
             <icon>LDS icon name</icon>
            </image>
            <color>CSS color definition</color>
          </lane>
        </lanes>
        <card>
          <title>Module field name</title>
          <showfields>
            <field>Module field name</field>
            ...
          </showfields>
          <morefields>
            <field>Module field name</field>
            ...
          </morefields>
        </card>
    </map>
```
Here is a custom template you can try:
```xml
    <map>
        <module>Accounts</module>
        <lanefield>rating</lanefield>
        <showsearch>1</showsearch>
        <showfilter>1</showfilter>
        <applyfilter>all</applyfilter>
        <pagesize>6</pagesize>

    <lanes>
        <lane>
            <name>Acquired</name>
            <sequence>1</sequence>
            <color>red</color>
       </lane>
       <lane>
            <name>Active</name>
            <sequence>2</sequence>
            <color>red</color>
       </lane>
       <lane>
            <name>Market Failed</name>
            <sequence>3</sequence>
            <color>red</color>
       </lane>
       <lane>
            <name>Project Cancelled</name>
            <sequence>4</sequence>
            <color>red</color>
       </lane>
       <lane>
            <name>Shutdown</name>
            <sequence>5</sequence>
            <color>red</color>
       </lane>
    </lanes>

        <card>
          <title>accountname</title>
          <showfields>
            <field>industry</field>
          </showfields>
          <morefields>
            <field>email1</field>
            <field>phone</field>
          </morefields>
        </card>
    </map>
```

<div class="notices blue">
Only module and lanefield are mandatory.
</div>

<br>
------------------------------------------------------------------------

[Next](../21.pivot) | Chapter 24: Pivot View.

------------------------------------------------------------------------