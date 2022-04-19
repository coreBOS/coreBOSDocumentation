---
title: 'Upsert Workflow Task'
---

Upsert Workflow Task
====================

This workflow task will permit us to create or update records in the
application. It is like the create workflow task but not limited to
related modules and the update workflow task all in one.

You must select the module you want to create/update the record in. You
can only select one module, which means that all the fields you select
in the field mapping must belong to the module you select first. If you
need to create/update records in different modules you have to add more
upsert workflow tasks, each one with one module.

Then you select a condition business map. This condition defines the
action that will be taken:

-   if the business map returns a positive integer, the task will look
    for a record with that ID and update it
-   if the business map returns a zero, the task will create a new
    record
-   if the business map returns a negative number that row will be
    skipped
-   if there is no map, we always create

Finally, you have to define a value for each field you want to create
and update. Note that since there can be no relation between the module
triggering the workflow task and the module where the new record is
being created you must establish a value for the relation fields
(getIDof is your friend here).

&lt;WRAP center round info 80%&gt; the first test I did was creating a
contact from an account. I did not set the accountid field expecting the
task to do it for me (like the create task does). I triggered the task
and didn't see any contact in the Accounts related list. I did that
three times before I noticed the error. I had three new contacts in the
contact module that were not related to the account. &lt;/WRAP&gt;

This task has a few interesting tricks up its' sleeve.

The most impressive is that it can loop over a set of rows and upsert
for each one. It is the first workflow task that can do this (it won't
be the last now that we have context support). If you load an array of
values into the *upsert\_data* context variable, the upsert task will
loop over each row, evaluate the business map, and upsert accordingly
for each one.

For each loop, it loads the data into the context variable:
*current\_upsert\_row*, so you have access to all the information in
each iteration, you can use in the field mapping like this (for example)

    getFromContext('current_upsert_row.quantity')

If you define a context variable named *linkmodeid* and set its' value
to the CRMID of a record in the application, the new record that is
created will be related to that CRMID. This is to easily support many to
many relations (Documents for example).

If you load [an attachment
definition](/en/devel/corebosws/docenhance_examples) into the virtual
"attachments" field, the task will upload the file into the field.

<table>
<thead>
<tr class="header">
<th>filename</th>
<th><code>array with these fields:
  name: string, name of the file to upload,
  size: file size
  type: file type
  content: base64_encode(file)</code></th>
</tr>
</thead>
<tbody>
</tbody>
</table>
