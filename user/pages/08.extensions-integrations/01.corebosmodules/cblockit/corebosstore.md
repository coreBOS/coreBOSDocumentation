---
title: 'Lock Record extension'
metadata:
    description: 'This extension will inform about record editing and optionally block the edit completely. When you access a record in detail view and another user in the application is editing it, you will be informed it is being edited.'
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
        - module
---

This extension will inform about record editing and optionally block the edit completely.
When you access a record in detail view and another user in the application is editing it, you will be informed it is being edited. Optionally you can activate a full block, so, if you try to edit the record you will not be permitted to do so until the other edit finishes.
This work is based on Stefan Warnat's work as he donated the initial version to the coreBOS project. Thank you!!

===
