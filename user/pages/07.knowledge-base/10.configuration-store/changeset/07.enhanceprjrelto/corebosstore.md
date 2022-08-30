---
title: 'Separate RelatedTo field on Projects'
metadata:
    description: 'This enhancement will separate the Account/Contact RelatedTo field on the Projects module.'
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

This enhancement, which is coreBOS Updater compatible and does not
modify any base files, will separate the Account/Contact RelatedTo field
on the Projects module.

The current field will be used for Accounts, so all records that are
related to accounts stay the same. If the ticket is related to a
Contact, the current value in the RelatedTo field will be copied to the
new Contact field and the RelatedTo field will get filled in with the
Account related to the selected Contact.

<div class="notices red"> This change can <strong>NOT</strong> be undone.
Once the changeset has been applied we must work with both fields
separated. </div>


<br>
------------------------------------------------------------------------

[Next](../08.enhancerelproject2qsopoi) | Chapter 15: Relate Projects with Quotes, Sales Orders, Purchase Orders and Invoices.

------------------------------------------------------------------------