---
title: 'Upgrade from vtiger CRM 5.4.0 to coreBOS 5.4.0'
---

Upgrade from vtiger CRM 5.4.0 to coreBOS 5.4.0
==============================================

&lt;WRAP center round info 70%&gt;The process detailed below is valid,
but, the existence of coreBOS Updater has changed everything and made
upgrading and keeping up to date MUCH easier. [The process detailed here
is easier](/en/upgradevt2cb).&lt;/WRAP&gt;

This first set of changes is basically paperwork; apply all the patches
and enhancements we have developed along the way and that have been
shared in the developer's list and trac.

[You can find the full details of the changes made on this
page](/en/devel/upgradevt2cb54changes).

Many of those changes will be useful by themselves if you have a vtiger
CRM 5.4. You can apply only those you need individually but I encourage
you to upgrade to coreBOS 5.4 because after this upgrade it is just
going to get better and we will be adding a lot of interesting things.

Upgrading is work better suited for a developer who is comfortable
playing with the code, but I will try to explain the process in detail
to make it easier.

&lt;WRAP center round alert 70%&gt; **Backup your files and database**,
there should be no problem, all the code is tested and the process is
not invasive, if there is a problem **we will help**, this is just a
precautionary step and another good reason to make a backup of your
information &lt;/WRAP&gt;

You have a clean vtiger CRM 5.4
-------------------------------

You can proceed in two ways, either use the fully patched zip upgrade
package or apply the patch.

### Fully patched zip upgrade

1.  backup your files and database, there should be no problem, all the
    code is tested, if there is a problem we will help, this is just a
    precautionary step and another good reason to make a backup of your
    information
2.  ![download the upgrade package from
    here](/devel/vtigercrm54_to_corebos54.zip)
3.  copy it to the root of your current vtiger CRM 5.4
4.  unzip it overwriting all files
5.  you can also uncompress the files locally and upload them to your
    server via FTP
6.  execute the database changes, there are only two changes and some
    files that aren't used anymore are eliminated.
    1.  Go to your browser
    2.  login to your coreBOS 5.4
    3.  edit the URL box and eliminate all the text starting from
        index.php
    4.  add upgrade2coreBOS.php&lt;WRAP center round info 60%&gt;

It should look like
this:`http://your_server/your_crm/upgrade2coreBOS.php` &lt;/WRAP&gt;

1.  execute the script and you should get a green screen with some
    messages about the actions executed, at the end of the screen you
    should have none of the steps in red

Your done. Enjoy!

### Apply patch file with changes upgrade

1.  backup your files and database, there should be no problem, all the
    code is tested, if there is a problem we will help, this is just a
    precautionary step and another good reason to make a backup of your
    information
2.  ![download the upgrade patch from
    here](/devel/vtigercrm54_to_corebos54.diff)
3.  copy it to the root of your current vtiger CRM 5.4
4.  apply the patch with the patch command (use tortoise if you are in
    windows)`patch -p 1 < vtigercrm54_to_corebos54.diff`
5.  you can also do this locally on your file system and then upload the
    files to your server via FTP
6.  execute the database changes, there are only two changes and some
    files that aren't used anymore are eliminated.
    1.  Go to your browser
    2.  login to your coreBOS 5.4
    3.  edit the URL box and eliminate all the text starting from
        index.php
    4.  add upgrade2coreBOS.php&lt;WRAP center round info 60%&gt;

It should look like
this:`http://your_server/your_crm/upgrade2coreBOS.php` &lt;/WRAP&gt;

1.  execute the script and you should get a green screen with some
    messages about the actions executed, at the end of the screen you
    should have none of the steps in red

Your done. Enjoy!

You have a clean vtiger CRM 5.4 with the security patch
-------------------------------------------------------

You can proceed in two ways, either use the fully patched zip upgrade
package or apply the patch.

### Fully patched zip upgrade

1.  backup your files and database, there should be no problem, all the
    code is tested, if there is a problem we will help, this is just a
    precautionary step and another good reason to make a backup of your
    information
2.  ![download the upgrade package from
    here](/devel/vtigercrm54security_to_corebos54.zip)
3.  copy it to the root of your current vtiger CRM 5.4
4.  unzip it overwriting all files
5.  you can also uncompress the files locally and upload them to your
    server via FTP
6.  execute the database changes, there are only two changes and some
    files that aren't used anymore are eliminated.
    1.  Go to your browser
    2.  login to your coreBOS 5.4
    3.  edit the URL box and eliminate all the text starting from
        index.php
    4.  add upgrade2coreBOS.php&lt;WRAP center round info 60%&gt;

It should look like
this:`http://your_server/your_crm/upgrade2coreBOS.php` &lt;/WRAP&gt;

1.  execute the script and you should get a green screen with some
    messages about the actions executed, at the end of the screen you
    should have none of the steps in red

Your done. Enjoy!

### Apply patch file with changes upgrade

1.  backup your files and database, there should be no problem, all the
    code is tested, if there is a problem we will help, this is just a
    precautionary step and another good reason to make a backup of your
    information
2.  ![download the upgrade patch from
    here](/devel/vtigercrm54security_to_corebos54.diff)
3.  copy it to the root of your current vtiger CRM 5.4
4.  apply the patch with the patch command (use tortoise if you are in
    windows)`patch -p 1 < vtigercrm54security_to_corebos54.diff`
5.  you can also do this locally on your file system and then upload the
    files to your server via FTP
6.  execute the database changes, there are only two changes and some
    files that aren't used anymore are eliminated.
    1.  Go to your browser
    2.  login to your coreBOS 5.4
    3.  edit the URL box and eliminate all the text starting from
        index.php
    4.  add upgrade2coreBOS.php&lt;WRAP center round info 60%&gt;

It should look like
this:`http://your_server/your_crm/upgrade2coreBOS.php` &lt;/WRAP&gt;

1.  execute the script and you should get a green screen with some
    messages about the actions executed, at the end of the screen you
    should have none of the steps in red

Your done. Enjoy!

You have a modified vtiger CRM 5.4
----------------------------------

There is not much I can say here; you need a developer to weed through
the changes and adapt your version with the new changes. We are tending
towards making these updates less traumatic but, at this moment, we
still have a little bit to go.

Your developer will have to evaluate which of the previous two scenarios
is best for him and take it from there.

You have your vtiger CRM 5.4 under GIT version control
------------------------------------------------------

This is ideal as you can add a remote to our [GitHub project
(https://github.com/tsolucio/corebos)](https://github.com/tsolucio/corebos)
and follow our development as we move along. You still have to play
around with the code and apply patches but GIT is going to help you a
lot.

So the steps here are identical to the three situations described before
just that GIT will do the patching for you and help you along the way
once you have added the remote link.
