---
title: 'Email tracking: Access count'
metadata:
    description: 'coreBOS incorporates a very basic email access counter.'
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
        - adminmanual
    tag:
        - tracking
---

coreBOS incorporates a very basic email access counter. When sending an email it automatically adds a 1x1 transparent image to the email. If the receiver of the email accepts this image, a call will be made to the application to get it. We will send the image and also register the access count in the system.

===

Obviously this is not fail-proof. Not only can the user open the email and not open the image, in which case we would not know he opened it, but also, it could happen that the image be accepted but the person really doesn't read the email.

For this to work, we must have the tracking script publicly available. The script lives at:

```
http://your_server/your_coreBOS/modules/Emails/TrackAccess.php
```

Since this does pose a security risk as you are exposing your application URL, we have added the possibility to **disable this functionality**. You can create a Global Variable called ***EMail_OpenTrackingEnabled*** for the Emails module and set it's value to 0. With that, the application stops adding this image to the outgoing emails.

If you do want to keep this functionality but protect your install you can configure your webserver (apache) to let this happen. In general, we recommend that all your coreBOS installs be behind an [Apache Authentication Scheme](https://httpd.apache.org/docs/2.2/howto/auth.html). This gives your data a first level of protection that your information deserves. Under this setup, none of your files are accessible without an initial user and password. That means that not even the TrackAccess.php that the email needs to count the access can be read, so it can't do its work. To overcome this we can add exceptions to the Authentication Scheme. For Apache .htacces this would look like this:

```
AuthType Basic
AuthName "Your Company Name"
AuthUserFile your_password_file
require valid user

<FilesMatch "^/modules\/Emails\/TrackAccess\.php$">
Allow from all
Satisfy Any
</FilesMatch>
```

The exception is established in the "FilesMatch" directive. You can get more information on this in the apache link above.

<div class="notices blue">
To overcome the many limitations of this approach to email tracking <strong><a href="http://coreboscrm.tsolucio.com/">coreBOS CRM</a></strong> has a full integration with <strong><a href="http://sendgrid/">SendGrid</a></strong> which not only gives us information about the access but will also inform us of deliveries, failed deliveries, clicks on different options in the email, automatic opt-out, and many other features. Contact us if you need more advanced options.
</div>

## Using Access count

The open count for each email is stored in the read only field called Access Count. You can use this field in filters, reports and workflows and it is included by default in the related lists of emails.

Each time the access counter is incremented a "save" event is launched against the email, so you can setup workflows to detect that and do other things.
