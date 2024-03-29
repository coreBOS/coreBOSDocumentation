---
title: 'Time/Resource Control'
metadata:
    description: 'This module adds time control to coreBOS.'
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
        - time
---

This module adds time control to coreBOS. The idea is that you will be able to register in the system time slots spent on the majority of the entities in the application. So a sales person can register time spent on a lead, a technician can register time spent on a trouble ticket or administration can register time spent on an invoice.

===

## Time/Resource Control

- **Project Demo** : [Time/Resource Control](https://demo.coreboscrm.com/)
- **Project Repository**: [Time/Resource Control](https://github.com/tsolucio/Timecontrol) module.

Some of the goals of this module are:

- a unique timecontrol identifier field
- start and end time with autocalculated total
- capability of being related to any module except products and services
- have a quick timesheet create button on each module's toolbar with preselection of the current module
- have a stopwatch create button on each module's toolbar with preselection of the current module
- multiple stopwatches with access to all the fields
- a separate product/service relation for invoicing
- invoiceable with special invoicing process
- support both individual and group taxing
- could be used to attach comments to entities, similar to the new modComments module
- eliminate the trouble ticket dependencies which complicate the code
- make timeresource entries visible on calendar, so you can control missing hours
- vtlib compatible, or at least as compatible as the new vtlib lets me

**Please consider donating, every little bit helps to keep up the ongoing effort.**

I need to thank many people for their interest and support. You know who
you are, and the others know who they are too :-)

Timecontrol is a module we've created to follow our previous Timesheets
and Timecards modules. Everything that could be done with the older
modules should be easier to do with the Timecontrol module, besides,
we've solved some issues and constraints.

The goal is to keep track of time associated to entities in coreBOS. A
running stopwatch will show the time currently spent for current tasks.
It should be easy to use and reliable.

Here's a short guide to start using it.

## How to use it

Creating a Timecontrol can be done by going to the Timecontrol module
and using the create button. Also, when viewing entities from other
modules that can be associated to a Timecontrol, a create button will be
shown in the toolbar, which will auto-fill the related entity field.

Most fields are optional, but filling the start date and time is always
required. Leaving the end time empty leaves the Timecontrol in the
running state. In this state, a running stopwatch is shown in the detail
view, by pressing the stop button the end time is set. The run/stop
state of the stopwatch depends on the end time being empty or not. This
way, the stopwatch doesn't ever get lost once created and it doesn't
stop counting either. Browsing, closing the window, quitting the browser
or even rebooting the machine won't reset the stopwatch.

When the stopwatch is stopped, a restart or resume button will be shown
in the detail view. Restarting a Timecontrol will duplicate it with the
start date and time set to now. This is useful when you want to restart
a past activity but there's a time gap in between. In case you need to
restart a Timecontrol as if it never was stopped you should edit it and
erase the end time, this way the stopwatch will start counting again
from the start time to now. There is another option, in the main module
you can find a variable:

`var $now_on_resume=true;`

If this variable is set to false, the dates of the new timecontrol will
not be set to "now" on resume. This can be useful when you have many
timecards to create that are in the past, so you avoid having to change
the dates on all duplicates. Not very useful, but it is there in case
anybody needs it.

The related concept picklist is just a way of classifying timecontrol
records, it wasn't intended for invoicing purposes, but to permit easy
filtering of records in custom views and reports if necessary. If you
are trying to register non-invoiceable time, that would be done by
leaving out the product/service. This is the main reason the
product/service is not mandatory. You can register time spent on
anything this way. Since it doesn't have a product it won't be
invoiceable and won't even show up in the list if you tick the "show
invoiceable" checkbox, and even if it does come up you won't be able to
select it for invoicing.

The module is directly related to all entities by default, so you will
be able to see the time spent on each entity in their more information tab.

Reporting is correctly supported.

**Press stopwatch in account detail view**

![Stopwatch](stopwatch.png?width=100%)

**Create new time/resource record**

![New TRControl](newtrc.png?width=100%)

**Stopwatch counting. Time running**

![counting](counting.png?width=100%)

**Stopwwatch stopped. Save record**

![Finished](finished.png?width=100%)

**Resume Stopwatch**

![counting](resume.png?width=100%)

## Convert from Trouble Ticket

Thanks to **Ted Janzen of [Janzen & Janzen ICT Services](http://www.j2ict.nl)** for this interesting enhancement.

We have a new action on the right panel of your tickets (and most other modules) that will open a new timecontrol record ready for creation.

## Explanation on forum

[Here is a forum thread](tcexplanationforum.pdf) where I try to explain the functionality with an example.

And here an extract of that thread:

The idea behind timecontrol is that you or anybody else working on the
TT registers the time and material used when he uses it with a
description of what has been done. For example, we have a TT for a
client who has called in because his computer doesn't start.

- tech calls to do initial diagnosis: creates a TC indicating that he spent 8 minutes to find out the computer can't find harddisk and setup a visit to client
- tech starts a new timecontrol with no end time, the stopwatch starts and the tech goes to the client
- tech stops TC on arrival so trip time is controlled
- tech starts new TC with no end time, so again stopwatch starts
- tech works on the computer and has to change the harddisk
- when he finishes he edits the TC, indicates the work he did, sets the end time and selects the service. elapsed time is automatically calculated
- he creates a new TC selecting harddisk product used
- etc

This example could be done for a lawyer, having meetings with his client
and using certain materials or paperwork in his name and many other
situations.

So in the end we have a complete set of all the time and material used
to solve the TT. You can report on this total time and even convert it
directly into an invoice with the timecontrol invoicing extension.

### Another person asking a similar question, and my answer

**Question:**

After looking at the demo I'm not quite sure how to use the module correctly.

Here's our use case. Someone brings in a laptop with a problem. We work
on the laptop for an hour to determine what the problem is. We want to
record the amount of time spent on the laptop but we do not bill based
on time. We would add a a service item "PC repair" with a price of $80
and during this time we determine it needs a new hard drive. We then
want to add the hard drive product to the ticket. Later when the hard
drive arrives we would want to add more time to keep track of our costs.
The final ticket should be invoiced showing the service item "PC Repair"
and the hard drive, but no time. How would I accomplish that?

Also I'm not seeing how to create the invoice in the demo.

**Answer:**

+ Laptop arrives: you create a Trouble Ticket (TT)
+ When you start your work you start a TimeControl (TC) record associated to the TT, no end time so counter starts It is important that you do NOT select any product or service for this TC.
+ When you finish you edit the TC and set the end time. It is important that you do NOT select any product or service for this TC.
+ Now you create a new TC with 1 unit of service item "PC Repair". You set an end time on this TC so the counter doesn't start. It doesn't matter what end time, the logical assumption would be a few minutes to represent "administrative tasks".
+ Either now or when the hard drive arrives you create a new TC with 1 unit of the product "Hard Drive"
+ You add more TC with the time spent to change the hard drive. It is important that all TC that only represent time do not have a product or service associated.
+ When you finish you go to the Timecontrol Invoicing extension (from the menu).
+ In the parameter section you select invoice per unit and any other options you may want.
+ Search for the TCs related to this TT. Only the ones with a product or service associated will be invoiceable, so although you will see the TC with time on them, you can't accidentally select them (you could directly hide them with the option in the search box). **Note**: we have a small hack that makes this really easy if you just need to invoice on a TT by TT basis and not mass invoicing which is the default.
+ Create invoice

Another option would be to create the TC that represent only time with a
product or service but 0 units. This way you could put the time and
comments on the invoice without charging it.

## Reporting: Totals

Thanks to [THORSMANN Co, Norway](http://www.thorstein.info), we have
created a new module that permits to easily report on time spent by our
users. Although the time control extension modifies the reporting system
to support reporting on time elements it is still difficult to obtain
reports that totalize time by users and dates. With this new extension
the system will automatically sum the time control records of each user
on each date. There is absolutely no additional work to be done, the
extension will detect when a time control record is being created,
modified or deleted and automatically do whatever is needed to keep the
total sum of time invested by each user.

This new module, benefits from all of coreBOS functionality, so we can
easily create filters or use the reporting system on the module to
retrieve total time of users during a week.

In the detail view of the module we can see a related list of all the
timecontrol records that represent the total.

The new extension is installed in the demo.

![List View](tctotalslv.png?width=100%)
![Detail View](tctotalsdv.png?width=100%)
![Report](tctotalsreport.png?width=100%)

### Future enhancements

Going forward it would be interesting to permit the reporting system to
filter on fields in the related timecontrol records. If anyone is
interested in taking this up contact me.

## Invoicing

The invoicing extension is installed separately from the time/resource
control module. This extension is being sold at **60 euros**. You can
make payment on our paypal account: paypal at tsolucio dot com and send
me proof of purchase to info at tsolucio dot com and I will send it to
you. It is totally vtlib compatible and installed through the module
manager.

A time/resource record **must** have an account **AND** a
product/service to get invoiced. The account will be the company the
invoice gets created against and each time/resource record will be
converted into a product line on the invoice which is why we need them
to have a product/service. We have created the extension intelligent
enough to be able to quote time spent on those entities that have an
account associated. For example, you can pick time spent on a quote, a
salesorder or a trouble ticket and we will use the associated account on
these entities as the invoicing account. This also applies to entities
that have the account not directly associated. You can also invoice time
spent on a contact and even on a trouble ticket or potential related to
a contact (not an account).

Basically you can invoice almost any time introduced in the system.

If you are trying to register non-invoiceable time, that would be done
by leaving out the product/service. This is the main reason the
product/service is not mandatory. You can register time spent on
anything this way. Since it doesn't have a product it won't be
invoiceable and won't even show up in the list if you tick the "show
invoiceable" checkbox, and even if it does come up you won't be able to
select it for invoicing.

**NOTE:** Since having each timecontrol record associated with a
product/service is mandatory to get it invoiced. We have created a
vtiger CRM modification with which you can assign a default
product/service to each user in their Preferences screen. Once
established, when a user creates a new timecontrol record this default
product/service will be automatically selected. Contact me if you are
interested.

This is the invoicing page where Timecontrols can be searched and invoiced.

![TRControl Invoicing](trcinvoicing.png?width=100%)

### Timecontrol Parameters

This first block of fields will permit us to select the timecontrol
records we have available for invoicing. We can select by date, assigned
user, account/contact and invoiced or not. The "show invoiceable" check
box will filter the timecontrol records that cannot be invoiced.

### Invoicing Parameters

The invoicing parameters block contains fields that will define how the invoice will be created.

-   **Invoice per**. Each timecontrol record will be converted to an
    invoice line. The units of the line will either be the units field
    of the timecontrol record or the time spent on the record converted
    to hundredths. With this parameter we can invoice time control
    records like resources. For example, 2 modules of RAM. You would put
    the RAM product in the selected product and then set the units field
    to 2.
-   **Timecontrol Grouping**. This determines the options to group
    timecontrol records on the same invoice
    -   None. Each timecontrol record is converted into an individual
        invoice line, even though we may repeat products/services
    -   Product. Timecontrol records with the same product/service are
        grouped together in one unique invoice line. The units or total
        time is summed.
    -   Related Entity. Timecontrol records with the same
        product/service that belong to the same related entity are
        grouped together in one unique invoice line. The units or total
        time is summed. This option implies product grouping (this can
        be changed, contact me). For example, if we have spent 2 hours
        of service1 on a trouble ticket, and another hour of service1 on
        a quote, in product grouping we would get one line of service1
        for 3 hours, in related entity grouping, we will get two invoice
        lines, one with 2 hours (trouble ticket) and another for 1 hour
        (quote)
-   **Tax mode**. The tax mode of the new invoices.
-   **Product description**. This defines how we fill in the comment
    field on the invoice line. Some of these options are incompatible
    with the grouping option, but the program will not recommend or warn
    you in any way.
    -   None. Comment will be left empty
    -   Timecontrol. The description on the timecontrol record will be
        used. Ideal when grouping is none. The initial date will be
        appended.
    -   Related entity. The identifier of the related entity will be
        filled in. Ideal when grouping is related entity.
-   **Entities Invoiced**. Set of entities that can be invoiced. These
    are the entities directly related to account in some way: account,
    contact, potential, invoice, quote, salesorder and trouble ticket.
-   **Assign Invoice to**. User the new invoice will be assigned to. The
    Account's User option will assign the new invoice to the same user
    the invoice account is assigned to.
-   **Subject**. the subject or reference of the new invoices
-   **Contact Related**. If marked, the process will look for a contact
    related to the account who has the special "Invoice Reference"
    checkbox marked and relate the invoice also to this contact.
-   **Contact Billing Address**. If marked, the process will look for a
    contact related to the account who has the special "Invoice
    Reference" checkbox marked and set this contact's address
    information as the new invoice address fields.

<span></span>

 ! We haven't gotten around to implementing Currency of the new invoice

 ! The invoicing options are saved in the database each time the search is executed. The idea is that you define the way your company invoices, save it and forget about it as it will always be the way you have configured it. That is why the invoice parameter block comes up closed by default. In the vast majority of cases you will not need to validate these values.

## Creating from Email

This is a very good idea we have been proposed by a client. It hasn't
been created yet but if anybody is interested I leave the details here
so that you can know that it is possible and defined.

We would like to modify the mail converter to accept the creation of
timecontrol records associated to the ticket. The idea is that once you
have the converter setup to accept ticket creation from your clients and
follow through with the whole conversation we would like to extend that
so the user working on the ticket can easily send an email to vtiger CRM
and have a timecontrol record created.

The process would be like this:

- select an email of the conversation, this email will have a header in the format **Re: ticket number and subject** the ticket number and subject are the ones you have configured when you setup mail converter
- click on respond
  - change the email "to" address to the email of customer support
  - change the "Re:" in the subject to "TC:"
  - change the body with the following syntax:
      - start: yyyy-mm-dd h:m
      - end: yyyy-mm-dd h:m
      - time: h:m
      - units: n
      - Description: text
  - send the email

The logic would be:

- if start and/or end are missing, time must be present and the program will use the time of reception of the email as the end time and will subtract the given time to obtain the start. If either start or end are given, the time will be added/subtracted from it to obtain the other necessary value.
- if time is not given, then start and end must be present to calculate the total time
- if units is not given, 1 will be used
- if there is no description, none will be used
- the created timecontrol record will:
  - use the email subject as text reference
  - be related to the trouble ticket
  - be related to the product that the ticket is related to

## Enhancements: Looking at other time control services (toggl)

- Manual edit can already be done adding the records either directly in full edit mode or through quick edit and with the new enhancements of autocomplete capture it will be pretty close. At most we may need some sort of grid view to make it easier to add entries.
- tags would be the category picklist or an additional text custom field could be added
- billable is the product/service capture and timecontrol invoicing.
- one line create
- offline functionality
- mobile app
- graphic reports

**Todo**:

- Grid view entries.
  - related to (autocomplete)
  - start (time)
  - stop (time)
  - date, default today (will be used for both start and stop, always TCs on the same day)
  - category (tag)
  - product (autocomplete)
- one line create
- offline functionality
- mobile app
- graphic reports

## FAQ

> Is it possible to add a part number option to tickets and have the parts used in the tickets to get reduced from the inventory? I may need to use 2 to 3 part nos. to fix one TT in Vtiger.

This is what TimeControl is for. The official name of this extension is: Time and
Material Control. Note that with a TC record you can also associate a
product or service to the TT, so with TC you can register all the time
and material used to solve a ticket. Then you can invoice both as needed.

<hr>

> We purchased the invoicing extension but, unfortunately, the text/description on the TC is not included in the invoice. It must be entered by hand for each invoice text!

Please read the section on **Invoicing Parameters** above which details your options:

If I understand you correctly, you are looking to modify the "Timecontrol Grouping" (=none) and "Product Description" (=Timecontrol).

Play with those a little and let us know how it turns out.

## Pending

- <s>support both individual and group taxing</s> Thank you [Duss Home Support](http://dusshome.com/)
- <s>make timeresource entries visible on calendar, so you can control missing hours</s>
- Currency of the new invoice
- <s>Reference. All invoices are created with the text "Batch Timecontrol", I would like to make this text available to the user through this configuration screen.</s>
- <s>Relate time/material records with sales orders exactly the same as with invoices for those companies that base their business on SO</s>
- <s>Relate time/material records with purchase orders exactly the same as with invoices, to be able to "buy" the time used by our workers.</s>
- add the current view timecards related list report: this probably won't be done, we are currently evaluating extending PDFMaker to support this feature.
- <s>support project (operation?) invoicing</s>
