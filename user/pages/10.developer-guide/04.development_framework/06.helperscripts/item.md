---
title: 'Helper Scripts'
metadata:
    description: 'Helper Scripts'
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
        - tool
    tag:
        - helper
---

In the **build/HelperScripts** directory you can find a series of small scripts and tools that are useful to achieve some of those special tasks that help adapt the system to your specific needs. Some of these should be done directly inside the application, and hopefully, someday they will be, but in the meantime, these are the steps to get it working.

===

addActionLink.php
-----------------

This is an example script to show how you can add an action link in the
right panel of the detail view of an existing module. In this case, it
is adding an **Add Ticket** action link to the Accounts module.

<div class="notices blue"> This script is no longer necessary.
The Business Actions module permits us to create links of all types
directly inside the application with a much more flexible permission
system. That said, the script still works but is not the recommended way
to create links anymore. </div>

addEntityMethod.php
-------------------

This is an example script to show how to associated a workflow custom
method to a module. You can [read more about it here.](../11.develtutorials/13.addworkflowfunction)

addModComments.php
------------------

<div class="notices blue">This is not needed anymore, you can
now go to Settings > Module Manager > ModComments > Settings
and activate it there.</div>

This script adds the comment functionality to any module. Copy it to the
root of your install and execute in the browser with the module name you
want to have the feature:

```
http://your_server/your_corebos/addModComments.php?modulename=Timecontrol
```

<div class="notices red">
Remember to delete the file when you are finished. </div>

composerinstallmodule.php
-------------------------

This is the composer installer worker script. It is in charge of
launching the install/update of modules installed using
[composer](https://getcomposer.org/). More on this can be read in the
Perspective Initiative.

convertTextFieldToPicklist.php
------------------------------

This script converts a uitype 1 text field into a picklist respecting
all the current values in the field. It accepts two parameters:

-   module: the name of the module which contains the field to transform
-   fieldname: the name of the field to convert

coreBOSEvents*
---------------

Script to load and show the functionality of the [coreBOS Eventing system](../11.develtutorials/20.corebos_hooks)

deleteModule.php
----------------

This is an example script to show how to delete a module

evalwf.php
----------

This script is for debugging the workflow process. It executes a given
workflow, against a record and gives us the result of the evaluation of
the conditions on screen. If the workflow is a scheduled workflow it
will show us the full SQL generated. If it is an event based workflow it
will tell us if it evaluates to true or false for the record.

runwftask.php
-------------

This helper script is a utility to manually execute one task inside a
given workflow against a given entity in the system. We basically use
this to debug workflows that fail for some reason and have more than one
task. Once you know which task is failing you can concentrate on that
one to debug it.

installmodule.php
-----------------

This is an example script to show how to install a module from its
manifest.xml file when all files are already copied into place in the
filesystem

installupdater.php
------------------

This script is a copy of the installmodule.php script specifically
tailored to installing the [coreBOS updater](../11.develtutorials/08.corebosupdater)
module.

stressTest.php
--------------

Script that creates 100 records and then deletes them. We use this one
to test time impact of the optimization changes we make :-)

<div class="notices red">
Please do not leave this files in the
root of your install. Remember to delete the file when you are
finished.</div>

dumpdatabase.php and addAuditModtracker.sql
-------------------------------------------

The dumpdatabase script will create a MySQL dump of your database
leaving out the potentially big tables of audit trail and module
tracker. This is very useful when those table get VERY big (as they do
on long living installs) both to get a copy of the database to debug
some behavior and to make faster backups during the work week leaving a
full dump for company low or downtime.

The addAuditModtracker.sql script will create the tables so you can use
the database.

<div class="notices blue"> 
<a href="https://github.com/omarllorens">Thank you Omar.</a>
</div>

composer2readme and module2wiki
-------------------------------

These PHP scripts will connect to a standard coreBOS module or extension
directory structure and output a DokuWiki syntax page with a summary of
the module or extension which you can use as a starting point to
document it in [our extensions section](../../../11.others/07.extensions).

    php build/HelperScripts/composer2readme.php https://raw.githubusercontent.com/tsolucio/coreBOSEmployee/master
    php build/HelperScripts/module2wiki.php https://raw.githubusercontent.com/tsolucio/coreBOSEmployee/master

setEmailOptOut
--------------

This script permits you to easily set the emailoptout field on or off by
calling a simple link. This is an easy, yet insecure way of being able
to add an "unsubscribe" link to the body of your emails.

As with most of the HelperScripts, copy the script to the root of your
install and set the URL to

    https://your_server/your_corebos/setEmailOptOut.php?email={email}&optout={0|1}&appkey={appkey}

this script triggers workflows accordingly.

**The correct and secure way to do this is using Web Services**
