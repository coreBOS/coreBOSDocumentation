---
title: 'Duplicate Merging'
---

Duplicate Merging
=================

Duplicate record detection gives you the capability to detect and handle
duplicate record. The merge feature helps you manage system storage
consumption and maintain data quality by freeing the system from old,
obsolete, or invalid data. Detection rules can be defined for different
record types, including custom entities etc.

#### Feature

Using Duplicate merge functionality user can merge two records found in
any module and can deactivate the duplicate record. This feature queries
your database in search of duplicate records. When you find and merge
duplicate record information, the duplicated records are then removed
from vtiger, and only the relevant record and data is retained. User can
choose master record at the end which will remain active and other will
get deactivated.

#### Modules Supported

Merge facility is available for almost all modules and especially
customized for the modules

-   Organizations
-   Contacts
-   Opportunities
-   Leads
-   Products
-   HelpDesk / Support Tickets
-   Vendors

### Functionality

1\. For all modules which have this feature will have a merge icon in
mini icons list. This will provide a form to select the fields(Merge
criteria) depending on which CRM will return duplicate records. In this
form, we can see two lists of records named 'Available Fields' and
'Selected Fields'. We can choose any number of fields from Available
Fields list and copy to Selected fields list using arrow buttons. Click
on Find duplicates button to proceed.
<img src="/en/mergeicon.png" class="align-center" />

If any two records which have the same values in all the fields (and
condition) chosen in merge criteria (Selected Fields) will be treated as
duplicates and all these duplicate sets will get displayed in duplicates
listview. <img src="/en/selectfieldsmerge.png" class="align-center" />

When we click on the merge button a window will be displayed where we
can find the options to choose record values from any of the records.

<img src="/en/mergerecordsinaccounts.png" class="align-center" /> Here
We can select one record as parent record, from which we want to save
the maximum number of fields and some from others.

Click on the merge button to merge the records.

Next time when the user again comes to this form it shows the last
selected criteria.

2\. You can also delete any set of selected records and the
deduplication process will reload with the new set of duplicates.

3.- You can also use the "Delete Exact Duplicates" button which will
massively eliminate all the records in each group of duplicate values
found except one. Note, this blindly deletes all records except one in
each group so you may lose information.

#### Merging records during Import

When a user imports records to a module, in Step 3 of the import process
there are two options:

1.  Manual merge.
2.  Automatic merge.

<img src="/en/manualmerging.png" class="align-center" /> If the user
selects a manual merge it shows all duplicate records in imported
records with Entity Type as Existing or Imported now. While merging user
can not select just imported record as parent record.

<img src="/en/duplicateleads.png" class="align-center" />

Finding and merging duplicate records is optional while importing. In
import step 3 user can select merge option otherwise it will work like
normal import. But if user select auto merge it will show two options

1.  Skip duplicate record – which will skip all duplicate records in the
    imported file.
2.  Overwrite duplicate records – will overwrite the existing duplicate
    record with the imported record.

<img src="/en/automerging.png" class="align-center" />

#### Merging Permissions

We can add/remove the permissions to find duplicates for a particular
profile. The modules which supports duplicates merging will have an
extra utility called 'Duplicates Handling'

<img src="/en/enableduplicatehandling.png" class="align-center" />
