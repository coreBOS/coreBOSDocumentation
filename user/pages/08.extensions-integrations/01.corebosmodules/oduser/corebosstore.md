---
title: 'OnDemand User module'
metadata:
    description: 'This extension modifies coreBOS to control the number of active users that are permitted to use the system. It was created to support On-Demand hosting services so you will be able to limit the users accessing the system and enforce per-user costs.'
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

This extension modifies coreBOS to control the number of active users that are permitted to use the system. It was created to support On-Demand hosting services so you will be able to limit the users accessing the system and enforce per-user costs.

===

### Fields

#### OD User Information

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
<td>User Name</td>
<td>106</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Status</td>
<td>picklist</td>
<td>Active,Inactive</td>
</tr>
<tr>
<td>First Name</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Last Name</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Client Accounts</td>
<td>relation</td>
<td>Accounts</td>
</tr>
</tbody>
</table>
<br>
#### Description

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
<br>
#### Custom Information

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
<td>Assigned To</td>
<td>assigned to</td>
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
<br>
Description
===========
<br>
#### Customized On-Demand CRM

Each time the admin user tries to create a new user, first they get a
license screen that informs them of the extra charge for each user and
asks them to confirm, if they do then they are taken to the normal user
creation screen.

Upon user creation, the new user is created normally and all the
information is sent to a centralized coreBOS (ODController) and inserted
into this new ODUser module which holds the basic information of the new
user.

When a user is eliminated from the client's CRM, the elimination request
is sent to the central coreBOS (ODController) and the user is marked as
eliminated with the date of elimination.

Create a service cron in the client's CRM that connects once a month to
the central ODController and writes the space consumed by the storage
directory and eliminates temporal files

Todo

-   add check box for acceptance
-   change the label to Accept
-   send new user info to ODController
-   send delete user info to ODController
-   prepare diff for other OD setups
-   space service cron

#### Customized ODController

-   We add our clients to Accounts, with additional information for OD
    service control
-   We install the module ODUser, such that one Account has many ODUsers
    and one ODUser has one Account
-   We create a new recurring invoice cron to generate an invoice for
    all accounts that are active. This invoice will create one product
    line for each non-deleted ODUser associated with the account and, as
    an option, add another product line for space consumption if this is
    important
-   These invoices will be automatically sent by email using GenDoc
    workflow

Todo

-   add new ODControl block in Accounts
    -   start date of OD service
    -   end date of OD service
    -   deactivated
    -   space consumed up to now
    -   invoice with tax
    -   frequency
-   add uitype 10 to accounts on user
-   new module ODUser
-   invoicing cron

#### Setup process

We create a website service with which a client can start his OD CRM
install and start working. This will be a webform with the necessary
information to automatically create the account in ODController, verify
payment (if necessary), and automatically execute the necessary steps to
have his ODCRM install ready for use.

-   Install ODUser
-   Create web service user
-   Configure mods2sync
-   Configure CentralSync
-   Install CentralSync in On-Demand coreBOS

Todo

-   webform
    -   invoice with tax
-   process webform
    -   create account
    -   user
        -   create user account
        -   update install x\_syncuser

Functionality
=============
