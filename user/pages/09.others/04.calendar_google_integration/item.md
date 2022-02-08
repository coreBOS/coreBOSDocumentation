---
title: 'Google Integration in Calendar module'
---

Google Integration in Calendar module
=====================================

Google Synchronization
----------------------

You can view or synchronize your Google events with your coreBOS events
using the Calendar. Firstly you have to [set up your Google
account/credentials](/en/calendar_google_integration#configuring_your_connection_with_google_calendar).

-   In case you have more calendars within your Google account, please
    select the calendar which you would like to use. Please note that
    one activity type can be synchronized with only one Google calendar.

<img src="/en/corebos/calendar/4_4_google_sync_settings.png" class="align-center" width="600" />

-   An additional step is to define export and import i.e.
    synchronization:
    -   Export “activity\_name” to calendar – checked means that all new
        created events in the Calendar will be also exported and visible
        in the Google calendar. In addition any change of these events
        will be synchronized towards Google calendar. These events are
        marked with an icon.
    -   Import from calendar to “activity\_name” - checked means that
        all new created events in Google calendar will be also visible
        in the Calendar. In addition any change of these events in
        Google calendar will be synchronized towards the Calendar. These
        events are marked with an icon and are not editable on the
        Calendar side.
-   Click on the \[Save\] button to save the synchronization settings.

The Calendar allows you to add Google events into coreBOS (see blue link
“Add into coreBOS” in the below picture). Please click on this link to
add this event to coreBOS.

<img src="/en/corebos/calendar/4_5_synchronized_google.png" class="align-center" width="700" />

&lt;WRAP center round important 70%&gt;Important note: Events added from
Google to coreBOS have to be updated/edited/moved in the Calendar only
(not in the Google calendar) in order to synchronize the changes done in
the Calendar towards Google calendar.&lt;/WRAP&gt;

Separating Events/Calendars
---------------------------

??? The problem I am facing is that personal events that I have on my
Google calendar are showing up on my task list in coreBOS. How can I get
this to stop? I do not keep 2 calendars and I prefer to work with only
one. I see in calendar settings that "Google is connected" for my user
name. Is this why my task list is picking up everything from my Google
calendar?

!!! Have a [read at this page](/en/calendar_google_separating_events)
for some indications.

Setup calendar event synchronization
------------------------------------

In the image below you can see a simple example of synchronization with
Google via separate activity “*Google events*”. These are the steps:

-   Using CRM Settings &gt; Picklist Editor create a new Activity Type
    for “Events” called “*Google events*” (you can name it as you wish).
-   In your Google calendar create a new separate calendar – in the
    example the name used was *ITS4You meetings* (again, you can name it
    according to your needs).
-   Set up synchronization with Google calendar by clicking on the small
    "down" arrow that appears when you hover over the newly created
    event.
-   You will see that “*Google events*” are visible in both Calendars
    with a separate activity type and color.

<img src="/en/corebos/calendar/6_1_synch_with_google.png" class="align-center" width="600" />

We implement this approach so it is easy to define which events should
be imported to and from Google. It is also suitable in case you don’t
need to synchronize your activities with Google anymore and you want to
deactivated it.

Configuring your connection with Google Calendar
------------------------------------------------

&lt;WRAP center round important 70%&gt;**Starting at coreBOS release
December 2014**&lt;/WRAP&gt;

We have updated Google Integration from API v.1 *(already deprecated by
Google)* to the newest API v.3.

The integration is being done through Web Application Client ID, which
lets a user login to Google Calendar in the background by previously
entering these parameters:

-   API Key,
-   Client ID.
-   Client Secret
-   Redirect URL.

Due to Google Security issues, integration does not require user's email
password anymore. So you just have to configure the parameters above and
validate the **admin user**, the rest of users, just need to click on
the ***Authorize and Connect*** link to give permission to the admin
user to manage and share their calendars.

Here is a step by step guide to help you configure your Google Account.
-----------------------------------------------------------------------

1.- Go to the link <https://console.developers.google.com/project>

2.- Create your project

<img src="/createproj.png" class="align-center" width="700" />

3.- Go to the Project. Click API in **APIs&auth** section and activate
the Calendar API

<img src="/calendarapi.png" class="align-center" width="700" />

4.- Go to the Credentials section and create the Public API Key by
clicking **Create New Key**. Choose Server Key

<img src="/createapikey.png" class="align-center" width="700" />

5.- Create Web Application by clicking **Create New Client ID** in the
OAuth section. Choose Service Account Option
<img src="/en/crear_id_cliente_1.png" class="align-center" width="700" />

6.- For permit you to create this Client ID , you have to set the values
for you Authoritation Screen.

<img src="/en/pantalla_de_autorizacion.png" class="align-center" width="700" />

7.- Now you can finish to config the Client ID, here is important that
you write the url to your coreBOS/sync.php in Redirect URI. For example:
**<http://yourcorebos.com/sync,php>**.

<img src="/en/crear_id_cliente_2.png" class="align-center" width="700" />

### After that, you can see the all data that you need to config Calendar4You.

<img src="/en/todos_los_datos.png" class="align-center" width="800" />

8.- Now access to your coreBOS like a admin user to copy the last
parameters in Calendar4You **settings**

<img src="/en/administrator.png" class="align-center" width="350" />

9.- Press on **Settings** icon to paste the next value in the next
window.

<img src="/en/settings.png" class="align-center" width="250" />

-   API Key,
-   Client ID.
-   Client Secret
-   Redirect URL.

<img src="/en/calendar_settings_1.png" class="align-center" width="700" />

### The checkbox, **insert from Google?** is for read the old and new events that you create in you Google Calendar and create this events in you Calendar4You in coreBOS.

<img src="/en/calendar_settings_2.png" class="align-center" width="700" />

#### Now you can press Save button to verify this data and if this date is correct the window will be close.

11.- After to save the previous data, you have click again in
**Settings**
<img src="/en/settings.png" class="align-center" width="250" /> and you
can see that you can clic in a new link called **Authorize and Connect**
, for permit coreBOS to manage your calendars. Now this Authorization is
for the actual google user that you have connect in your browser. If you
disconnect, you will can to choose an other user to give this
authorization

<img src="/en/authorize_and_connect_1.png" class="align-center" width="700" />

<img src="/en/authorize_and_connect_2.png" class="align-center" width="700" />

11.- After to permit, you can to select your calendars to add a event
type like a Meetings

<img src="/en/select_calendars.png" class="align-center" width="700" />

12.- Now your configuration is done, and the rest of users just have to
access to their Calendar4You , try to add a google calendar to a event
type and in the first time they will see the famous **Authorize and
Connect** link.
<img src="/en/omar_llorens.png" class="align-center" width="250" />

<img src="/en/omar_authorize_connect_1.png" class="align-center" width="700" />

##### Click on the link , permit coreBOS to manage the calendars and finally you will can to select your calendars to your event types.

<img src="/en/omar_authorize_connect_2.png" class="align-center" width="700" />
<img src="/en/omar_authorize_connect_3.png" class="align-center" width="700" />

13.- Just an other thing. For active the Calendar4You Crons to sync the
events with Google Calendar, you have to go to coreBOS Settings -&gt;
Scheduler the last two crons that you can see the next image.

<img src="/en/cron_tasks_c4y.png" class="align-center" width="700" />

That's it. Enjoy!

Considerations
--------------

-   Google calendar update cron updates only **NOT HELD**
    events:&lt;code&gt; (vtiger\_activity.status != 'Held' OR
    vtiger\_activity.status IS NULL)&lt;/code&gt;
-   Deleting the event from google calendar doesn't delete it from the
    calendar in Corebos just from the table of google cal events
-   Deleting a google calendar event from Corebos is done one by one
    (just for the deleted records) using the beforedelete handler.
