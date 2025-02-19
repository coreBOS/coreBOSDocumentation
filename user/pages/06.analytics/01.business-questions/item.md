---
title: 'Business Questions'
metadata:
    description: 'Menu Editor'
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
        - analytics
        - businessquestion
    tag:
        - analytics
---

## SQL Query. Filter Conditions

When "SQL Query" is marked:

- the Columns are meant to be a comma-separated list of columns
- the Conditions field is meant to be a correct list of joins and a where conditions
- the sort and group by also must be a correct column specification

When "Conditions in Filter Format" is marked, the Conditions are supposed to be a JSON array specification of fields and conditions grouped as per the syntax followed in the filter system. For example:

```
[[{"field":"subject","op":"c","value":"an","glue":"or"},{"field":"pl_gross_total","op":"g","value":"20","glue":""}]]
```
```
[[{"field":"subject","op":"c","value":"an","glue":"or"},{"field":"pl_gross_total","op":"g","value":"20","glue":"and"}],[{"field":"pl_gross_total","op":"l","value":"20","glue":""}]]
```

with these columns should work:

```
subject,quote_no,pl_gross_total
```

## Materialized Views

Adds the functionality of creating materialized views, which are based on coreBOS database tables.

The Business Question module stores the configurations for each materialized view.

<div class="notices blue">
Note that in MySQL 5.x, which is the version used by coreBOS, materialized views are not supported yet. Subsequently, we are going to create physical tables in order to mimic the functionality of a materialized view.
</div>

A Business Question configuration would be composed of the following attributes:

-   Name of the materialized view
-   SQL Query flag, which indicates that the materialized view should be created based on a SQL query. Optional.
-   Module - this is the primary module of the materialized view
-   Unique ID Field - this serves as a unique identifier of the records of the materialized view
-   SQL Query - contains the SQL SELECT query which determines the data that should be copied into the materialized view.
-   Columns - list of materialized view's columns. Optional.
-   Condition - contains the conditions of the SQL query. Optional.

There should be inserted some useful actions in the DetailView of each Business Question:

-   Test SQL - runs the SQL query against the database and returns a success / no success message.
-   Create Materialized View - creates the physical database table, populated with data from the SQL Query defined in the Business Question
-   Remove Materialized View - drops the materialized view
-   Add Materialized View Workflow - creates two workflows in the Module specified in cbQuestion: one workflow on each save and the other on delete.
-   Delete Materialized View Workflow - drops the workflows at the Module specified in Business Question.
-   Add and Delete Materialized View cron - creates a scheduled task that will delete and update the materialized view on the defined frequency. You must review that the scheduled task is set and defined correctly.

When using the workflow approach, we could run into a situation where we create an inconsistent view. The way the workflow updates the view is on each save of the main module. The code finds the row in the view that has changed and updates it. Now let's suppose that the view is retrieving information from a related table. For example, our view is on project tasks and it contains information from the related project. If any of that information on the Project changes, our view will not update the corresponding rows.

If we want a historical view, the behavior described may be desired, but if we want to update the rows, we have to activate the "Update View when Related Changes" checkbox and define the related module we want to control in the "Related Module List" picklist.

The code will activate a scheduled task that will retrieve the related information that has changed since the last execution and update all affected rows. Note that this must be done in the background as the number of affected rows can be potentially very high.

Finally, if we are using a custom SQL written manually and that query has an alias on the main module table and/or on the crmentity table, we must indicate the name of those aliases in the corresponding fields in order for the application to know where to modify the query for individual row updates.

## File Exports
Business questions support a "File" type which will generate a CSV dump of the question. This file will be saved in the cache directory and the path to the file returned.

The File type has an extended properties syntax that permits us to define the details of the generated CSV file. The complete properties object looks like this:

```
{
  "delimiter":"single character to use as field separator. defaults to comma",
  "enclosure":"single character to enclose strings that contain the delimiter",
  {
    "format": {
      "date":"Y-m-d", // format to use for date fields
      "float":{       // format to use for decimal/currency fields
         "decimalseparator":".", 
         "grouping": ",",
         "numberdecimals": "4"
      }
  },
  "columns": [ // definition of the labels of the columns and the format of the field
    {
      "label": "l1",
      "type": "float"
    }
  ],
  "nodatesuffix": true //definition of not adding the date to the filename
}
```

So we can define all the details of the CSV file formatting.

The column labels are positional. That means that if you want to put a label on the fifth column you must set also the first four.

## Mermaid Graphs
A mermaid graph is defined by putting the body of the markdown inside the "Columns" field and the Mermaid graph type in the "Properties" field. Like this:

![](cbmermaid01.png?width=100%)

If we want to add some styling on the nodes and links we can use the standard mermaid syntax to do so adding the markdown directly in the columns field, like this.

![](cbmermaid02.png?width=100%)

We can also use a more advanced property definition to establish node and link styling that can be determined depending on the context of the record we are showing the graph in. This functionality is based on the ModTracker extension. Once ModTracker is tracing the changes in a module, the graph can receive a list of all the transitions a field has gone through and we will be able to style each node and link depending on the path followed by the record.

The idea is that we can have a process established in a module. This process is related to a field in the module that passes through some states. For example, the sales stage picklist in Potentials. As the opportunity is worked on, the different sales stage states are selected. At any given point in the life of the opportunity, we can load a mermaid graph that will ask ModTracker which have been the changes that the record (the sales stage field) has gone through, and for each one, we will be able to apply a style.

With this functionality you will see a different style on each record you open in detail view, reflecting the transitions in the life of each particular record. If you show the mermaid graph above, where the styling is fixed in the "columns" field, you would always see the same graph on all records which is not what you need to show the user.

The extended syntax looks like this:

```
{
"graph" : "LR",
"defaults":{
  "nodestyleaccepted": "fill:greenyellow,stroke:green,stroke-width:4px",
  "nodestylerejected": "fill:greenyellow,stroke:blue",
  "linkstyleaccepted": "stroke:greenyellow,stroke-width:2px",
  "linkstylerejected": "stroke:green,stroke-width:4px"
},
"nodes":[
  {
   "nodename":"B",
   "condition": "44061",
   "nodestyleaccepted": " fill:yellow,stroke:green,stroke-width:4px"
  },
  {
   "nodename":"D",
   "condition": "44061",
   "nodestylerejected": "fill:red,stroke:red"
  }
],
"links":[
  {
   "linkposition": "4",
   "condition": "44061"
  },
  {
   "linkposition": "3",
   "linkstylerejected": "stroke:red,stroke-width:4px"
  }
]
}
```

The only nodes and links that will be styled are those that the record has gone through, all the others will use the default mermaid styling.

If a node has a condition, the business map will be executed, if it passes the "*styleaccepted" will be applied, and if not the "*stylerejected". If either of them are empty, or there is no condition the styling rules defined in the "defaults" section will be applied.

The node and link MUST appear in the definition section or they will not be styled.

## Potentials Example

```
A((Prospecting)) --> D
B((Qualification)) --> D
C((Analysis)) --> D
D((Proposal)) --> E
E((Decision)) -->F
F((Perception)) --> G
G((Quote)) --> H
H((Review)) --> I((Won))
H --> J((Lost))
```

```
{"graph" : "LR",
"defaults":{
 "nodestyleaccepted": " fill:greenyellow,stroke:green,stroke-width:4px",
 "nodestylerejected": "fill:greenyellow,stroke:blue",
        "linkstyleaccepted": "stroke:greenyellow,stroke-width:2px",
        "linkstylerejected": "stroke:green,stroke-width:4px"
},
"nodes":[
{
 "nodename":"A",
 "nodestate":"Prospecting",
 "condition": "44177",
 "nodestyleaccepted": " fill:greenyellow,stroke:green,stroke-width:4px",
 "nodestylerejected": "fill:greenyellow,stroke:blue"
},
{
 "nodename":"B",
 "nodestate":"Qualification",
 "condition": "44177",
 "nodestyleaccepted": " fill:greenyellow,stroke:green,stroke-width:4px",
 "nodestylerejected": "fill:greenyellow,stroke:blue"
},
{
 "nodename":"C",
 "nodestate":"Needs Analysis",
 "condition": "44177",
 "nodestyleaccepted": " fill:greenyellow,stroke:green,stroke-width:4px",
 "nodestylerejected": "fill:greenyellow,stroke:blue"
},
{
 "nodename":"D",
 "nodestate":"Value Proposition",
 "condition": "44177",
 "nodestyleaccepted": "fill:greenyellow,stroke:green",
 "nodestylerejected": "fill:greenyellow,stroke:red"
},
{
 "nodename":"E",
 "nodestate":"Id. Decision Makers",
 "condition": "44177",
 "nodestyleaccepted": "fill:greenyellow,stroke:green",
 "nodestylerejected": "fill:greenyellow,stroke:red"
},
{
 "nodename":"F",
 "nodestate":"Perception Analysis",
 "condition": "44177",
 "nodestyleaccepted": "fill:greenyellow,stroke:green",
 "nodestylerejected": "fill:greenyellow,stroke:red"
},
{
 "nodename":"G",
 "nodestate":"Proposal/Price Quote",
 "condition": "44177",
 "nodestyleaccepted": "fill:greenyellow,stroke:green",
 "nodestylerejected": "fill:greenyellow,stroke:red"
},
{
 "nodename":"H",
 "nodestate":"Negotiation/Review",
 "condition": "44177",
 "nodestyleaccepted": "fill:greenyellow,stroke:green",
 "nodestylerejected": "fill:greenyellow,stroke:red"
},
{
 "nodename":"I",
 "nodestate":"Closed Won",
 "condition": "44177",
 "nodestyleaccepted": "fill:greenyellow,stroke:green",
 "nodestylerejected": "fill:greenyellow,stroke:red"
},
{
 "nodename":"J",
 "nodestate":"Closed Lost",
 "condition": "44177",
 "nodestyleaccepted": "fill:greenyellow,stroke:green",
 "nodestylerejected": "fill:greenyellow,stroke:red"
}
],
"links":[
    {
        "position": "0",
        "from": "Prospecting",
        "to": "Value Proposition",
        "condition": "44177",
        "linkstyleaccepted": "stroke:blue,stroke-width:2px",
        "linkstylerejected": "stroke:green,stroke-width:4px"
    },
    {
        "position": "1",
        "from": "Qualification",
        "to": "Value Proposition",
        "condition": "44177",
        "linkstyleaccepted": "stroke:blue,stroke-width:2px",
        "linkstylerejected": "stroke:green,stroke-width:4px"
    },
    {
        "position": "2",
        "from": "Needs Analysis",
        "to": "Value Proposition",
        "condition": "44177",
        "linkstyleaccepted": "stroke:blue,stroke-width:2px",
        "linkstylerejected": "stroke:green,stroke-width:4px"
    },
    {
        "position": "3",
        "from": "Value Proposition",
        "to": "Id. Decision Makers",
        "condition": "44177",
        "linkstyleaccepted": "stroke:greenyellow,stroke-width:2px",
        "linkstylerejected": "stroke:green,stroke-width:4px"
    },
    {
        "position": "4",
        "from": "Id. Decision Makers",
        "to": "Perception Analysis",
        "condition": "44177",
        "linkstyleaccepted": "stroke:blue,stroke-width:2px",
        "linkstylerejected": "stroke:green,stroke-width:4px"
    },
    {
        "position": "5",
        "from": "Perception Analysis",
        "to": "Proposal/Price Quote",
        "condition": "44177",
        "linkstyleaccepted": "stroke:blue,stroke-width:2px",
        "linkstylerejected": "stroke:green,stroke-width:4px"
    },
    {
        "position": "6",
        "from": "Proposal/Price Quote",
        "to": "Negotiation/Review",
        "condition": "44177",
        "linkstyleaccepted": "stroke:blue,stroke-width:2px",
        "linkstylerejected": "stroke:green,stroke-width:4px"
    },
    {
        "position": "7",
        "from": "Negotiation/Review",
        "to": "Closed Won",
        "condition": "44177",
        "linkstyleaccepted": "stroke:blue,stroke-width:2px",
        "linkstylerejected": "stroke:green,stroke-width:4px"
   },
   {
        "position": "8",
        "from": "Negotiation/Review",
        "to": "Closed Lost",
        "condition": "44177",
        "linkstyleaccepted": "stroke:greenyellow,stroke-width:2px",
        "linkstylerejected": "stroke:green,stroke-width:4px"
    }
]
}
```

This is how the Business Question looks:

![](cbmermaid05.png?width=100%)

This is how the Detail View widget looks in a potential record that has followed the defined steps:
![](cbmermaid04.png?width=100%)

and this is how it looks on a potential record that has not followed the defined steps:

![](cbmermaid03.png?width=100%)

This is the Business Action definition

![](cbmermaid06.png?width=100%)

```
block://DependencyGraphBlock:modules/cbQuestion/DependencyGraphBlock.php:targetid=$RECORD$&qnid=44181&targetfield=sales_stage

```

where "44181" is the crmid of the Business Question

and you must load the Mermaid library to convert the markdown to a graph with another Business Action like this

![](cbmermaid07.png?width=100%)

```
modules/cbQuestion/resources/mermaid.min.js
```