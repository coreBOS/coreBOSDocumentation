---
title: 'Subscription-Follow Changes module'
metadata:
    description: 'Module that permits following changes on any record for any user. This module will send notifications to all users subscribed to a record.'
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

This module will allow you to activate notifications about changes in records. Each user will be able to activate the notices on the records they want by clicking on a link that will be available in the right panel of the record in the detail view of the entity or by multiple selection in the list view.

===

## Activate Follow Me on a module

Once the module is installed using the typical mechanisms coreBOS gives us for that, we can go to the Subscription module and access its configuration options. As a normal module it has the standard settings options but it also an additional one to activate the follow functionality per module: "Subscription Configuration".

![Subscription Settings](SubscriptionSettings.png?width=100%)

After activating the functionality we will see a "Follow" action panel in the detail view of each reacord.

![Follow me](FollowMeAction.png?width=100%)

This action will create records in the Subscription module that represent the status of each user with each record. When you stop following a record the record in the subscription module will be deleted.

Following a record means that you will get notifications each time:

- the record is modified. the email will contain a relation of the fields that have been changed
- the record is deleted
- the record is linked with another record
- the record is unlinked with another record

You can access the subscription module directly to mass create or delete them.

## Workflow blocking

This module has the additional functionality of blocking workflow emails. You can manually create a record in the module and select a workflow. In this case, any emails that workflow sends will not be sent to the user assigned to the record. The existence of the record acts as filter by eliminating the users' email from the workflow task.

## Email Templates

The installation of the module creates 6 email templates that will be used for the different notifications. These templates can be found and modified in the Message Template module.

![Notification templates](MsgTemplates.png?width=100%)

You can use the normal templating variables in these templates but it is rather hard as they are used for all modules so if you set a variable that makes sense for Contacts the template will not make sense for Invoices (for example), so try to keep the message short and generic.

The subscription module gives you some special variables you can use to overcome this limitation:

- `$custom-changedvalues$` a table with the relation of fields that have changed and their values
- `$custom-siteurl$` the application URL (so you can construct links)
- `$custom-module$` the module the record belongs to
- `$custom-recordid$` the CRMID of the record being changed
- `$custom-recordname$` the Entity Name of the record
- `$custom-linkmodule$` the module the record is being linked with
- `$custom-linkrecordid$` the CRMID of the record being linked
- `$custom-linkrecordname$` the Entity Name of the record being linked

<span></span>

 !! Note: in order to send these emails the subscrition module adds a manual workflow which should not be modified.



## Fields

### Subscription Information

<table class="table table-striped">
<thead>
<tr class="header">
<th>Field</th>
<th>Type</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr>
<td>Related Record</td>
<td>relation</td>
<td></td>
</tr>
<tr>
<td>Subscription No</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Related Module</td>
<td>relatedmodule</td>
<td></td>
</tr>
<tr>
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
<tr>
<td>Positive</td>
<td>ispositive</td>
<td></td>
</tr>
<tr>
<td>Created By</td>
<td>created_user_id</td>
<td></td>
</tr>
<tr>
<td>Created Time</td>
<td>datetime</td>
<td></td>
</tr>
<tr>
<td>Modified Time</td>
<td>datetime</td>
<td></td>
</tr>
</tbody>
</table>

### Description

<table class="table table-striped">
<thead>
<tr class="header">
<th>Field</th>
<th>Type</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr>
<td>Description</td>
<td>text</td>
<td></td>
</tr>
</tbody>
</table>
