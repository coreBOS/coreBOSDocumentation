---
title: 'Convert Country field to picklist'
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

This change will convert country fields on Accounts, Contacts, Vendors,
Leads and Inventory modules into shared picklists.

[Convert Country field to picklist](convertcountry2picklist.zip)

The changeset contains a hard-coded list of country values in English.
If you want that in another way or find some country missing you can
edit that array to your needs.

You must import this change using the import button that you will find
on the coreBOS Updater list view.

<div class="notices red">There is no support for undoing this
change yet. It wouldn't be difficult to undo so reach out if you need
that.</div>


<br>
------------------------------------------------------------------------

[Next](http://localhost/coreBOSDocumentation/knowledge-base/configuration-store//changeset/convertstate2picklist/id:e0e4593c729f937e8eaac0619f59d4bb/store:configuration) | Chapter 9: Convert State field to picklist.

------------------------------------------------------------------------