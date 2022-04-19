---
title: 'Select User for Calendar Follow up'
---

Select User for Calendar Follow up
==================================

This enhancement is a coreBOS Updater changeset which adds a user
picklist to the calendar records Follow-up block. That will permit you
to select a user for the follow-up record.

<embed src="/en/extensions/extensions/assignfollowupuserfield.zip" class="align-center" />

Two more steps must be taken for this change to work.

Change the workflows
--------------------

The follow-up record is actually created by two workflows:

      * Create Calendar Follow Up on create
      * Create Calendar Follow Up on change

These two workflows must be changed so that the assigned user of the new
record is updated from the new field, something like this next image:

<img src="/en/extensions/extensions/assignfollowupuserwf.png" class="align-center" />

Translate the field label
-------------------------

Go to the coreBOS Translation module and create any translation records
you may need. That will look something like this:

<img src="/en/extensions/extensions/assignfollowupuseri18n.png" class="align-center" />

---- dataentry ---- name : AssignFollowUpUserField type : enhancement
description\_wiki: Add secondary user picklist to Calendar to permit
assigning the follow-up task to another user. keywords\_tags : Calendar,
Follow-up, User version : 1.0 homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:enhancecalendarassignfollowup>
release\_dt : 2019-01-03 license : Vizsage price: 0 buyemail\_mail:
paypal(at)tsolucio(dot)com distribution: Sale authorname : JPL TSolucio,
S.L. authoremail\_mail :info(at)tsolucio(dot)com authorhomepage\_url :
<http://tsolucio.com> supportemail\_mail :info(at)tsolucio(dot)com

------------------------------------------------------------------------
