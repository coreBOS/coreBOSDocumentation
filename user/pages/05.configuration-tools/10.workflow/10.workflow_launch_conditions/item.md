---
title: 'Workflows Launch Conditions'
metadata:
    description: 'Launch conditions specify when the workflow must be executed.'
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
        - workflow
    tag:
        - conditions
        
---

Launch conditions specify when the workflow must be executed.

All workflows except scheduled are "save" event based, which means that they will be evaluated ONLY when a record is saved from within the application. That save event will usually be some user creating or editing a record, but it could also be triggered from a webservice call or by some specially crafted code.

Since workflows are triggered when we save a record the different launch options that we have are related to this event:

-   **Only on the first save**: Triggers the workflow when you create a
    new record. For example a welcome email would have this launch
    condition so it gets sent ONLY when the new contact is created.
-   **Until the first time the condition is true**: Triggers the
    workflow only once for a record that complies with the defined
    conditions. Once executed, your workflow will not trigger on the
    same record again. However, it will trigger actions on other records
    in the selected module when they fulfill the conditions. For
    example, when an invoice enters status paid we send a "thank you"
    email to the client. If we edit the invoice again and save it we
    don't want that email going out again for this record.
-   **Every time the record is saved**: Triggers the workflow every time
    you save a record, including the first creation save. This is ideal
    for calculated fields. For example the forecast amount field on
    opportunities uses this launch condition to calculate the forecast
    each time the record is saved.
-   **Every time the record is modified**: Triggers the workflow every
    time you edit and save your record, EXCEPT on the first creation
    save. For example, if we want to get an email each time a ticket is
    closed, we would use this launch condition so that even when a
    ticket is reopened and saved again we would get that email.

**Scheduled Workflows** are time based, not event based, so they are
triggered on a certain date/time. These are so important that they have
[their own documentation page](../05.scheduled_workflows)


<br>
------------------------------------------------------------------------

[Next](../11.workflow_stepbystep) | Chapter 2: Workflow step by step explanation.

------------------------------------------------------------------------