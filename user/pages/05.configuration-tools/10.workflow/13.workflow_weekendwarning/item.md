---
title: 'How to send emails/sms on specific week days'
metadata:
    description: 'How to use coreBOS to send email/sms on specific weekdays without having the need to code at all.'
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
        - howto
---

In this tutorial we are going to show you how to use coreBOS to send
email/sms on specific weekdays without having the need to code at all.

We are going to demonstrate this example on the module called Payments.
You can do these steps for every module on your coreBOS CRM.

Our task here is to send an email to a group of users every time a
Payment is created on specific days, in our case, **only** weekend days.

The first thing we are going to need is a new custom field (we are going
to call it "Day of the week", you can name it whatever you want).

This field will be of the **type "number"** and it will hold a number
from 1-7, representing each day of the week (1-Monday, 2-Tuesday...
7-Sunday).

The whole point is to use it as a condition to launch a workflow
(example: if DayofWeek==7, then launch X workflow).

How to create the custom field
------------------------------

To create a custom field we need to go the module where we are going to
create the workflow for: Settings-&gt;CRM Settings-&gt; Module Manager.

Here we find our module and then click on the
![](image8.png?width=3%) icon or the row.

Or we can just open our module and than click on the
![](image8.png?width=3%) icon.

![](image2.png?width=100%)

After this we go to **Layout Editor** and there we add our custom field
on the block we want (as shown below)

![Sample Vector](image1.gif?resize=750,300)

Now we have to create our custom field by clicking on the **"Add custom
field"** icon ![](image3.png?width=3%)

We have to select the **type "Number"**, Label can be any name you want
for your field and the length will be 1. You can leave the Decimal
Places empty. (See image below)

![](image10.png?width=100%)

Save it and we are ready to go.

After saving our new custom field, we can go back to our module to see
if it is displayed correctly.

The default value will be 0 but we will work on that in the steps below
so the field gets the number of the day of the week when the record is
saved/modified.

![](image6.png?width=100%)


We have to create a new workflow which will send the emails when the
conditions we want are completed. If you are new to workflows, [please check this link](../11.workflow_stepbystep).

Our workflow will consist of **2 tasks**.

First one will update the field "Day of the week" with the number of
current day of the week.

Second task will send the email.

Creating the Workflow.
----------------------

### Step 1

Create a new workflow (for our module) and save it. After saving it, it
will show options to add tasks to it. See image below

![](image4.png?width=100%)

### Step 2

Click on New Task and choose Update Fields and click Create.

![](image11.png?width=100%)

### Step 3

Put the title for the task (like "Update the Day of Week field"). Leave
the checkboxes as default and then click on "Add Field".

Choose your new custom field from the dropdown list (in this case "Day
of the Week") and click on the empty field next to it (which will bring
a pop-up for further procedures).

![](image12.png?width=100%)

### Step 4

We have to set the value for our custom field. Choose **Expression**
from the dropdown list and paste this code at the text area:

    format_date(get_date('today'), 'w')

This function will update our custom field with the number of the
current day of the week. Please check the GIF below for presentation.


![Sample Vector](image9.gif?resize=750,300)




### Step 5

After saving the first task, we will create another new task which will
send the email. Fill the fields with the values you want (email
recipients, body, subject, etc...).

We have to **Add Conditions** for the Send Email to be executed. In our
case we want **the task** to be executed **only** when the day of
payment creation is weekend. We do this by creating a new condition
group, choose our custom field (Day of the Week) and put the condition
we want. In this, case the condition is "greater than 5".

Or we can create 2 conditions, in one of them we put Day of Week equal
to 6 and in the other one, we put Day of Week equal to 7 joining them
with an "OR".

![](emailcondition.png?width=100%)
 
Save the task.

### Step 6

Make sure that the task to update the field is the first one in the
order.

![](taskorder.png?width=100%)

Click Save and give it a try.

[Thank you Besart!](https://github.com/besartmarku)


<br>
------------------------------------------------------------------------

[Next](../12.workflow_tricksandtips) | Chapter 13:Workflow Tricks and Tips.

------------------------------------------------------------------------