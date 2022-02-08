---
title: 'OneSignal Integration'
---

OneSignal Integration
---------------------

### Configuration

The [OneSignal](https://onesignal.com/) configuration [is really
simple](https://documentation.onesignal.com/docs/web-push-typical-setup).

1.  Create an account on OneSignal site. Go to the login page, click on
    "Sign Up" and follow the steps
2.  Create an App, for example, "coreBOS", select WebPush
3.  **Site Name**: set it to a name that identifies your install, this
    will usually be the name you have set in your coreBOS
4.  **Site URL**: the URL of your coreBOS install (must be publically
    accessible)
5.  upload an icon
    <img src="/en/integrations/onesignalsitesetup.png" class="align-center" />
6.  Configure the initial permission prompt. All users MUST accept that
    we send them notifications. The first time a user access coreBOS
    with OneSignal active, the permission prompt will appear. If they do
    not accept that we send them notifications, we will not be able to
    do so.
    <img src="/en/integrations/onesignalpermissionprompt.png" class="align-center" />
7.  Configure a welcome notification. This is not mandatory but it is
    good practice and validates that the authorization went correctly.
8.  Leave the Webhooks, Click Behavior, and Persistence in the advanced
    options at their default
    <img src="/en/integrations/onesignaladvanced.png" class="align-center" />
9.  The advanced options **Service Workers** settings may need
    modifications. If your coreBOS has its' own domain, which is the one
    you entered in Site URL above, then you can leave this option
    unchecked. If your coreBOS is installed in a subdirectory then you
    must check this option and set the name of the directory. Supposing
    that the coreBOS we are configuring is in a subdirectory named
    "reserveit", then our settings will look like this:
    <img src="/en/integrations/onesignalsw.png" class="align-center" />
10. Go to Keys & IDs: copy them into coreBOS settings
    (index.php?action=integration&module=Utilities&\_op=getconfigonesignal)
    and activate the integration
11. the next time a user logs in he will see the authorization
    notification
    <img src="/en/integrations/onesignalauth.png" class="align-center" />
12. from this point on coreBOS can send notifications to this user
    <img src="/en/integrations/asteriskincomingnotification.png" class="align-center" />

You can use the **Test** button that will appear once you have saved the
API key and ID to verify that the integration is working. It will send a
notification with a test message.

<img src="/en/integrations/testnotification.png" class="align-center" />

### Links

-   [OneSignal](https://onesignal.com/docs)
-   [Documentation](https://documentation.onesignal.com/docs)
-   [Database, DMP, & CRM
    Integration](https://documentation.onesignal.com/docs/internal-database-crm)
-   [Announcment Blog Post](https://blog.corebos.org/blog/onesignal)
