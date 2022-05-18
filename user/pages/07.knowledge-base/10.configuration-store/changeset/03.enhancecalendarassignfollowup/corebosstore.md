---
title: 'Select User for Calendar Follow up'
metadata:
    description: 'This enhancement is a coreBOS Updater changeset which adds a user picklist to the calendar records Follow-up block.'
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


This enhancement is a coreBOS Updater changeset which adds a user
picklist to the calendar records Follow-up block. That will permit you
to select a user for the follow-up record.

[coreBOS Changeset](assignfollowupuserfield.zip) <br>

Two more steps must be taken for this change to work.

Change the workflows
--------------------

The follow-up record is actually created by two workflows:

      * Create Calendar Follow Up on create
      * Create Calendar Follow Up on change

These two workflows must be changed so that the assigned user of the new
record is updated from the new field, something like this next image:

![](assignfollowupuserwf.png?width=100%)

Translate the field label
-------------------------

Go to the coreBOS Translation module and create any translation records
you may need. That will look something like this:

![](assignfollowupuseri18n.png?width=100%) 


<br>
------------------------------------------------------------------------

[Next](http://localhost/coreBOSDocumentation/knowledge-base/configuration-store//changeset/enhancecyprelto/id:1d423964124bfb1284851734767a0e3a/store:configuration) | Chapter 11: Separate Account and Contact field on Payments.

------------------------------------------------------------------------