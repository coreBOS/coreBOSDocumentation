---
title: 'How to implement a send email service'
metadata:
    description: 'How to implement a send email service'
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
        - sendemail
    tag:
        - howto
        - email
---

coreBOS has an abstraction layer for sending emails, instead of always sending with phpmailer, now we can define a class to send as we want. This allows us to integrate with other email delivery systems such as sendgrid or mailchimp without having to modify the code of the application.

In [this blog post](http://blog.corebos.org/blog/emailapisendgrid) you can get a general idea of the implications and next we will see how to implement a class of sending emails by studying the sendgrid integration code

The steps to implement an email sending system are

- implement a class with at least 3 static methods
- implement an event handler that returns the path and the name of the class
- register the handler

the class must implement these three methods

- public static function useEmailHook()
- public static function emailServerCheck()
- public static function sendEMail($to_email, $from_name, $from_email, $subject, $contents, $cc, $bcc, $attachment, $emailid, $logo, $replyto, $qrScan)

the **useEmailHook** method returns a true or false value depending on
whether the service is active or not. This allows us to implement a
simple way to activate and deactivate the service. If it returns false
we will use the default email delivery system

The **emailServerCheck** method returns a true or false value depending
on whether the service is configured or not. If it returns false we will
use the default email delivery system

The method **sendEMail** is the one that actually does the work of
sending the email. It receives all the information it needs to do that.
You can [read a little about the parameters in this blog post](http://blog.corebos.org/blog/sendemail). This method must return 1 on ok, any other value is error

Let's talk a little bit about these methods in our sendgrid
implementation. These are the methods
[useEmailHook](https://github.com/tsolucio/corebos/blob/master/include/integrations/sendgrid/sendgrid.php#L128)
and
[emailServerCheck](https://github.com/tsolucio/corebos/blob/master/include/integrations/sendgrid/sendgrid.php#L306)

we can see that the functionality of both is the same and is based
simply on whether the client has activated the service or not. We do not
check the configuration of the account in SendGrid.

[here you can see the sendEMail
method](https://github.com/tsolucio/corebos/blob/master/include/integrations/sendgrid/sendgrid.php#L132)

Now we implement the event handler that returns the name and location of
the class
```php
public function handleFilter($handlerType, $parameter) {
  global $currentModule;
  if ($handlerType == 'corebos.filter.systemEmailClass.getname' && corebos_sendgrid::useEmailHook()) {
    return array('corebos_sendgrid', 'include/integrations/sendgrid/sendgrid.php');
  } else {
    return $parameter;
  }
}
```

finally, we register the event handler
```php
global $adb;
$em = new VTEventsManager($adb);
if (self::useEmailHook()) {
  $em->registerHandler('corebos.filter.systemEmailClass.getname', 'include/integrations/sendgrid/sendgrid.php', 'corebos_sendgrid');
} else {
  $em->unregisterHandler('corebos_sendgrid');
}
```
With this, we just have to implement a simple way for the administrator
to register their data. We have done it in
```
module=Utilities&action=index
```

![](sendgridconfiguration.png?width=100%)

In the particular case of sendgrid, we also implement a capture of
events to mark the different states of the message as well as launch the
workflows. We built this using the notifications service of coreBOS
(notifications.php)
