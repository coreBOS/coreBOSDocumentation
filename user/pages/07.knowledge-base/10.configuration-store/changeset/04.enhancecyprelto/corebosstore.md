---
title: 'Separate Account and Contact field on Payments'
metadata:
    description: 'This enhancement will add a new Account field on the Payments module.'
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

This enhancement, which is coreBOS Updater compatible and does not
modify any base files, will extract the Account from the RelatedTo field
on the Payment module and create a new Account field.

<div class="notices red"> It will NOT copy any existing
values. It just creates the new field.</div>

Then it will add an event controller to set the value of the new account
field when we create a payment record from the related list of a
contact.


<br>
------------------------------------------------------------------------

[Next](../05.enhancehdrelto) | Chapter 12: Separate RelatedTo field on HelpDesk.

------------------------------------------------------------------------
