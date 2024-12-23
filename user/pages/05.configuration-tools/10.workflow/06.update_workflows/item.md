---
title: 'Update Workflow Tasks'
metadata:
    description: 'Update fields using workflow'
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
        - updaterecord
        - updatefield
        - workflow
---

Aggregations
------------

When you want to update a field from a workflow (even on a related
module), you have the option to use a function expression. There are
many options here, two of which are the 'aggregation' and
'aggregation\_fields\_operation' functions. The default output, once you
select one of these is:

    aggregation(operation,relatedmodules,relatedFieldToAggregate,conditions)

or

    aggregation_fields_operation(operation,RelatedModule,relatedFieldsToAggregateWithOperation,conditions)

Use this small guide to get you going:

-   For the 'operation' parameter, you have the following choices (I
    think they speak for themselves):
    -   sum
    -   min
    -   max
    -   avg
    -   count
    -   std
    -   variance
    -   group\_concat

The related module is the module you want to aggregate from. This can be
the same module as you're creating the workflow on. You would use this
if you want to update a field on a related record by summing up (for
instance) all the 'siblings' of the record you are editing. For
instance, you could update a field in Accounts with the sum of all
payments made to that account, whenever you edit or save one of those
payments, without having to save the Account in question first.

The related field(s) should be field names of the module you specified
in the previous parameter. Again, this can be one the same module you're
creating the workflow on.

The conditions should be an array-like formatted string with 4
parameters (example: \[relatedto2,e,$(relatedto2 : (LitigationMatter)
matter\_name),or\])

The first parameter tells the workflow which field to look for on the
'sibling' records.

The second is the operator. In the example, there is an 'e', which
stands for 'equals'.

The third parameter tells you what the fields in the 'relatedto2' field
on the sibling should match. In this case, a nested expression is used
to get the name of the related LitigationMatter, so basically you want
all 'siblings' that have the same name in that field

The last parameter tells the workflow how to 'glue' conditions together
if you have multiple (yes, you can have multiple condition arrays).

<div class="notices red">
IMPORTANT NOTE: Do not use spaces in the condition array-string between the arguments.
</div>

Examples
--------

### ***jgrossman** on discussion forum :: Hopefully someone can help me figure this out

I think it should be easy but I don't seem to be able to figure out how
to have a workflow that updates a field with a message that has an
expression with words and math together. So it would say *Your answer is
54 units to small*. The workflow would have in the expression the static
text of "Your answer is" then math to come up with the 54 using
(cf\_\#\#\# + cf\_\#\#\#) then back to static text for "units to small'.

!!! Ok, It turns out it is as simple as I thought. The code below works.

    concat('Your answer is ',cf_### + cf_###,' units to small')

###  Can you show us an example of an if-else formula?

!!! Sure, he is one that sets a currency field depending on a country field

    if cf_843 == 'Colombia' then 'USD' else if cf_843 == 'Madrid' then 'EURO' else if cf_843 == 'London' then 'GBP' else if cf_843 == 'Hong Kong' then 'HKD' else if cf_843 == 'Melbourne' then 'AUD' else ' ' end

Things to respect:

-   all on one line, no new lines for nice formatting, although it may
    work, it may not
-   simple quotes (') not double (")
-   the last else value has a space ('\[space here\]'), that is
    important, if you put an empty string ('') it will not work

### In a workflow update task, we want to use a formula like the below, in order to update the value of a field:

    if time_diffdays(cf_855,get_date('today')) > 60 then add_days(get_date('today'), 28) else '01-01-1970' end


That is, if the date in cf\_855 is more than 60 days in the future, then
the formula result is (today + 28 days), otherwise the formula result is
1-1-1970.

We have tried several different syntaxes but none of them are working.
Can you help?


There are two issues here that are based on the same principle: we are very limited in the possibility of embedding operations. With that I mean that workflow update formulas do not accept having an expression
inside an expression. So

<div class="notices red">
This is comment is not true anymore in coreBOS. We can now embed expressions inside expressions with no limitation. Althought the solution proposed here using intermediate fields is valid, you should be able to launch the original "if" expression now. </div>

    if time_diffdays(cf_855,get_date('today')) > 60 then...

is incorrect because the condition must be basic operations. Also,

    ...add_days(get_date('today'), 28)...

is wrong for the same reason.

So the solution is to use intermediate field calculations. In other
words, artificial custom fields that hold the calculated values we need
and also knowing that some base functions like add\_days or time\_diff
accept only one parameter and "*know*" that the other is "today".

The next image should achieve what you are asking:

![](calcwf.png?width=100%)


<div class="notices red">
Note that this is NOT time based, it will not calculate automatically when "today" is over 60 days, you will have to edit the record EVERY day to see the changes. As of March 2015 you can use scheduled workflows for time based workflows.
</div>


<br>
------------------------------------------------------------------------

[Next](../07.upsert_workflows) | Chapter 5: Upsert Workflow Task.

------------------------------------------------------------------------