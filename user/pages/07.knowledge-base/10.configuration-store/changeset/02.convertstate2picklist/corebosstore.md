---
title: 'Convert State field to picklist'
metadata:
    description: 'This change will convert country fields on Accounts, Contacts, Vendors, Leads and Inventory modules into shared picklists.'
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
        - extension
    tag:
        - changeset
---
---


This change will convert state fields on Accounts, Contacts, Vendors,
Leads and Inventory modules into shared picklists.<br>

[Convert State field to picklist](convertstate2picklist.zip)


The changeset contains two state CSV files, one for US and one for
Spain. You must define which one to apply editing the changeset BEFORE
applying it. You will find the code in the
```php
    build/changeSets/imported/convertState2Picklist.php
```

file and you must set the $importLang variable accordingly. You will
also find the two state files in the same directory and you can add your
own state files for your country by simply adding a new file and setting
the language extension accordingly.

You must import this change using the import button that you will find
on the coreBOS Updater list view.

<div class="notices red"> There is no support for undoing this
change yet. It wouldn't be difficult to undo so reach out if you need
that.</div>


<br>
------------------------------------------------------------------------

[Next](http://localhost/coreBOSDocumentation/knowledge-base/configuration-store//changeset/enhancecalendarassignfollowup/id:a8adcf692fa926fbb99ec90a190b5b8f/store:configuration) | Chapter 10: Select User for Calendar Follow up.

------------------------------------------------------------------------