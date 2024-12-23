---
title: 'Adding unit tests for new workflow operator'
metadata:
    description: 'Adding unit tests for new workflow operator'
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
        - development 
        - unittest
    tag:
        - workflow
---

the unit tests files you are looking for are in these two files

[https://github.com/tsolucio/coreBOSTests/blob/master/modules/com_vtiger_workflow/VTJsonConditionTest.php](https://github.com/tsolucio/coreBOSTests/blob/master/modules/com_vtiger_workflow/VTJsonConditionTest.php)

[https://github.com/tsolucio/coreBOSTests/blob/master/modules/com_vtiger_workflow/WorkFlowSchedulerQueryTest.php](https://github.com/tsolucio/coreBOSTests/blob/master/modules/com_vtiger_workflow/WorkFlowSchedulerQueryTest.php)

the JSONCondition is for the evaluation of the conditions you put in the workflow for non-scheduled trigger

so, in the screencast, you shared it would be the condition you put inside the workflow task

VTJsonCondtion is the script in charge of evaluating the condition

we have some tests but none related to "time"

let's see one

[https://github.com/tsolucio/coreBOSTests/blob/master/modules/com_vtiger_workflow/VTJsonConditionTest.php#L167](https://github.com/tsolucio/coreBOSTests/blob/master/modules/com_vtiger_workflow/VTJsonConditionTest.php#L167)

in this test, we are setting this condition

```
createdtime <= sub_days(start_date on service, 3)
```

to evaluate that condition, to see if it is true or false, we need a real record

in order to get a real value for the createdtime and date_start fields

that happens on line 163 and 164

then on line 168, we send the expression and the record (entityId) to be evaluated and get back true or false

the file is all full of examples like this

you have to add new tests here that will evaluate conditions for the month_day operation

so you will have to do something like:

```
[{"fieldname":"createdtime","operation":"month day","value":"02-22","valuetype":"rawtext","joincondition":"and","groupid":"0"}]
```

which, if I understood correctly, would be comparing the createdtime month and day of the record you evaluate with to the constant string '02-22'

the other script is for Scheduled trigger type

this trigger is fundamentally different from the other trigger types

when you set a workflow to an "on save" trigger (for example) the workflow will launch with ONE record, the one being "saved"

but the schedule trigger works differently.

it "wakes up" at the indicated time, so there is no record at that moment, there is no "save" event, it is time-based.

so, what corebos does is convert the conditions into an SQL query, it launches the query and gets a set of records

then it launches the workflow on each record found

so the tests are also different

with JSONCondition we get one record and evaluate the condition

with SchedulerQuery we will evaluate the conditions and check if the SQL that it returns is what we expect

let's see an example

[https://github.com/tsolucio/coreBOSTests/blob/master/modules/com_vtiger_workflow/WorkFlowSchedulerQueryTest.php#L55](https://github.com/tsolucio/coreBOSTests/blob/master/modules/com_vtiger_workflow/WorkFlowSchedulerQueryTest.php#L55)

the condition is for the invoice module and says
```
exciseduty >= sum_nettotal
```
so we expect a query that will return all the invoice whose exciseduty field is bigger than its sum_nettotal field

we execute the setup and getWorkflowQuery to obtain
```
SELECT vtiger_invoice.invoiceid FROM vtiger_invoice  INNER JOIN vtiger_crmentity ON vtiger_invoice.invoiceid = vtiger_crmentity.crmid  WHERE vtiger_crmentity.deleted=0 AND   (  (( vtiger_invoice.exciseduty >= vtiger_invoice.sum_nettotal) )) AND vtiger_invoice.invoiceid > 0
```
which looks correct

in your case you have added the month day operator so you will have to add tests like this
```
[{"fieldname":"createdtime","operation":"mont fay","value":"due_date","valuetype":"fieldname","joincondition":"and","groupid":"0"}]
```
and I would expect an SQL something like
```
SELECT vtiger_invoice.invoiceid FROM vtiger_invoice  INNER JOIN vtiger_crmentity ON vtiger_invoice.invoiceid = vtiger_crmentity.crmid  WHERE vtiger_crmentity.deleted=0 AND   (  (( DATE_FORMAT(vtiger_crmentity.createdtime, '%m-%d') >= DATE_FORMAT(vtiger_invoice.due_date, '%m-%d')) )) AND vtiger_invoice.invoiceid > 0
```
start asking