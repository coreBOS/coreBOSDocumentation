---
title: 'Segmentation Lists'
metadata:
    description: 'Module to register the different groupings of our clients by different criteria in order to work with them in a segmented manner.'
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

Module to register the different groupings of our clients by different criteria in order to work with them in a segmented manner.

===

### What are they and what are they used for

![segmentation chart](segmentacion.jpg?class=float-right)

List segmentation is exactly what it sounds like -- you divide up your
contacts into a bunch of smaller lists, or segments, based on criteria
you set.

These segments can be cut and combined in a number of different ways
based on lead intelligence. For instance, you can segment your contacts
based on psychographics, demographics, industry, company size -- you
name it.

Segmentation is important because it helps you better target and
personalize your campaigns and content. With better targeting comes
better conversion rates -- because you're sending the most relevant
information possible to your contacts.

This module allows you to group Accounts, Contacts, and Leads in
different lists with which we can perform joint marketing actions.

You can fill in the lists in different ways, from workflows, through
filters, reports or from the OpenStreetMap integration.

For example, we have a segmentation list of all the people who have
registered to the BLOG of coreBOS. As soon as they are registered, the
contact is created in our coreBOS and added to the BLOG segmentation
list. When we publish something new we massively send an email to
everyone on the list.

### How to relate entities with a segmentation

We have 3 ways to add or remove accounts, contacts and leads to a
segmentation list.

#### Manual

It is the traditional way, in which we access the related lists of the
segmentation and select or add accounts, contacts and/or leads.

With this option every time we add or remove an entity in the system we
must remember to go to the corresponding segmentation and make the
relevant operations.

#### Synchronized Filter

To avoid having to remember to synchronize the segmentation we have
added the option to link a filter to the segmentation. In this way, we
can create a filter in accounts (for example) and have all the accounts
contained in the filter directly available in the segmentation without
doing any additional task.

#### Workflows

Through the workflow task **Many to Many Relation Task** we can add and
remove accounts, contacts and leads individually when certain actions
occur in the system.

The biggest advantage with respect to the synchronized filter option is
that we can mix records with very different conditions instead of having
only those that belong to a filter.

#### Marketing Dashboard

By massively selecting different entities based on different
combinations of filters we can easily fill in segmentation lists.

#### OpenStreetMap Integration

When creating a radius search on the map we can find an option to send
all the records contained inside the circle to a segmentation list.
