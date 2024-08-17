---
title: 'Recurring Invoice setups'
metadata:
    description: 'Recurring Invoice feature, permits you to use a Sales Order as a template to generate Invoices on a regular frequency.'
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
        - module
    tag:
        
        - invoice
---

The **Recurring Invoice** feature, permits you to use a Sales Order as a template to generate Invoices on a regular frequency.

===

### Usage

A cron script in the system will launch once a day looking for all Sales Orders that have the **Enable Recurring** check box marked. For all of those it will look if the current date is inside the **Start and End Period** and finally, if the **Recurring Frequency** is due on this date. If so a new Invoice will be created with

- the indicated **Invoice Status**
- the **due date** for the generated Invoice will be set to **(Generated date + payment duration)**.

<div class="notices red">
The first invoice generated is the <strong>NEXT</strong> one after the start period. In other words, the expected behavior is to create a recurring Sales Order, set the start period to the first invoice to be generated and then create that first one manually. Then the system will take care of all the rest until the end period.
</div>

The recurring frequencies supported are Daily, Weekly, Monthly, Quarterly, Half-Year, and Yearly.

Following is a snapshot of the Sales Order creation page:

![Recurring Invoice SO](createsalesorderri.png?width=100%)

### FAQ

[Trac Ticket](trac8614.pdf)

<div class="notices blue">
<h2>last_recurring_date field isn't updated when modifying recurring frequency</h2>

<div style="color:red;">If you change the recurring frequency of an order, the last_recurring_date field from vtiger_invoice_recurring_info mysql table isn't updated accordingly. For example, if on 2015-08-13 you set a monthly recurring, the first invoice will be automatically created on 2015-09-13, and last_recurring_date will be set to that date. Then, if you update the frequency to daily, last_recurring_date will still be set to 2015-09-13 so you won't have any daily invoices before this date.</div>
<br><br>
I understand that you are saying that the recurring MONTHLY invoice was correctly created on 2015-09-13, then AFTER that date, for example on 2015-09-20 you changed the frequency to DAILY and you expect to have DAILY invoices BEFORE 2015-09-13. If that is the case I don't think that would be correct, you change the frequency after the invoice was created, you shouldn't get new invoices before that date, and you should start getting daily invoices from the day you change the frequency.<br><br>

In fact what IS wrong and maybe that is what you were trying to say, is that when you change the frequency to a lower one, since the last recurring date is not updated you will start getting invoices from that last date and not from the day you change the frequency. For example:<br><br>

In the example above, I had a monthly frequency that created an invoice on 2015-09-13. On 2015-09-20 my client asks me to change the frequency. Logically, I should edit the current SalesOrder and stop that recurrence, close this SO and create a new SO with the new settings, but, instead of doing that I decided to edit the SalesOrder and change all the details of the new invoices and the frequency to daily. In that case, what will happen is that I will start getting daily invoices from 2015-09-13 and not 2015-09-20, which is what I would expect.<br><br>

I guess we could detect if the frequency is lower than the current one (bigger ones have no issues) and change the last recurring date in those cases but I think it makes a lot more business sense to close the SalesOrder and create a new one to reflect the current relation with your client and not lose the historical situation you had before.<br><br>

HTH

</div>