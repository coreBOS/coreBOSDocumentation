---
title: 'Install coreBOS'
---

Install coreBOS
===============

Requirements
------------

-   Apache 2.x or above.
-   MySQL 5.x and 8.x
-   PHP from 7.1.x to 7.4.x. PHP 7.4 is recommended.

&lt;WRAP center round info 75%&gt; This is a typical **WAMP/LAMP
stack**. All linux distributions have this natively so we recommend you
install the packages from your distribution (make sure you have the
right versions). On windows download the XAMPP stack from apache
friends. You can see the [list of application versions
here](http://code.stephenmorley.org/articles/xampp-version-history-apache-mysql-php).
&lt;/WRAP&gt;

### MYSQL Requirements

Please make sure to review MySQL configuration (my.cnf or server start
parameters)

<table>
<tbody>
<tr class="odd">
<td>ENGINE=InnoDB</td>
<td>Should be available. (Turn off --skip-innodb)</td>
</tr>
</tbody>
</table>

### PHP Extensions

Following extensions should be enabled for your PHP setup

<table>
<tbody>
<tr class="odd">
<td>GD</td>
<td>Mandatory</td>
<td>Charts and graphs generation are dependent on this library.</td>
</tr>
<tr class="even">
<td>IMAP</td>
<td>Mandatory</td>
<td>Webmails Module is dependent on this library.</td>
</tr>
<tr class="odd">
<td>Zlib</td>
<td>Mandatory</td>
<td>Used for backups and module packaging among others</td>
</tr>
<tr class="even">
<td><strong>DOM (php-xml)</strong></td>
<td>Mandatory</td>
<td><strong>New dependency</strong> For coreBOS Updater</td>
</tr>
<tr class="odd">
<td>OpenSSL</td>
<td>Optional</td>
<td>Imap with OpenSSL should be enabled in case Mail server needs to be connected via SSL</td>
</tr>
<tr class="even">
<td>Curl</td>
<td>Optional</td>
<td>This one is optional but really important for any external communications, like SMS, Google Sync or RSS</td>
</tr>
<tr class="odd">
<td>MBString</td>
<td>Optional</td>
<td>This one is optional but mandatory if you want to use GenDoc</td>
</tr>
</tbody>
</table>

### PHP Configuration

Make sure to verify if your PHP configuration meets the recommended
values.

<table>
<thead>
<tr class="header">
<th>Variable</th>
<th>Value</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>allow_call_time_pass_reference</td>
<td>on</td>
</tr>
<tr class="even">
<td>error_reporting</td>
<td>E_ERROR</td>
</tr>
<tr class="odd">
<td>safe_mode</td>
<td>off</td>
</tr>
<tr class="even">
<td>display_errors</td>
<td>on</td>
</tr>
<tr class="odd">
<td>file_uploads</td>
<td>on</td>
</tr>
<tr class="even">
<td>max_execution_time</td>
<td>600</td>
</tr>
<tr class="odd">
<td>max_input_vars</td>
<td>6000</td>
</tr>
<tr class="even">
<td>post_max_size</td>
<td>36M</td>
</tr>
<tr class="odd">
<td>memory_limit</td>
<td>1024M</td>
</tr>
<tr class="even">
<td>log_errors</td>
<td>off</td>
</tr>
<tr class="odd">
<td>output_buffering</td>
<td>on</td>
</tr>
<tr class="even">
<td>register_globals</td>
<td>off</td>
</tr>
<tr class="odd">
<td>request_order</td>
<td>GP</td>
</tr>
</tbody>
</table>

&lt;WRAP center round info 85%&gt; The maximum size of file uploads is
defined by the PHP **upload\_max\_filesize** directive. Remember to set
this variable to accommodate the file size you need to upload. coreBOS
has a Global Variable that can limit the upload BELOW this directive,
never above, PHP defines the maximum limit.

I normally set this variable to 32Mb &lt;/WRAP&gt;

&lt;WRAP center round info 85%&gt; If you have the PHP Suhosin extension
installed, this extension adds restrictions to make PHP more secure, but
some of these restrictions break coreBOS.

To solve this problem you must change two variables in the suhosin
config file: (normally: /etc/php5/conf/suhosin.ini)

    suhosin.post.max_vars = 8000
    suhosin.request.max_vars = 8000

After this, you must restart your apache server. &lt;/WRAP&gt;

&lt;WRAP center round important 85%&gt; For security reasons it is
**VERY** important that you set the value of **request\_order** to
**GP**.

coreBOS barely uses cookies and it does not look for them in the
$\_REQUEST superglobal.

Most modern linux servers already set this value to GP by default so you
are probably already covered but check just in case.

You can [read a little more about this
here](https://www.owasp.org/index.php/PHP_Security_Cheat_Sheet#Use_of_.24_REQUEST).
&lt;/WRAP&gt;

### File Permissions

Provide read-write access to the following files and folder
(recursively):

&lt;WRAP center round important 60%&gt; Read and Write permissions
should be enabled for user/group who owns webserver process (like
www-data or httpd or apache). &lt;/WRAP&gt;

    *config.inc.php 
    *tabdata.php 
    *install.php 
    *cache 
    *storage/ 
    *install/ 
    *user_privileges/ 
    *Smarty/cache/ 
    *Smarty/templates_c/ 
    *modules/Emails/templates/ 
    *modules/ 
    *cron/modules/ 
    *test/vtlib/ 
    *backup/ 
    *Smarty/templates/modules/ 
    *test/
    *logs/ 
    *modules/Webmails/tmp/

&lt;WRAP center round important 60%&gt; Please make sure you meet all
these requirements &lt;/WRAP&gt;

Install
-------

-   Download the source code from GitHub
-   copy the code into a folder inaccessible from your web server
    install
-   type in the URL of the folder into your browser
-   you should get the **Configuration Wizard** welcome page

<img src="/en/corebosinstall01.png" class="align-center" width="800" />

-   click on the Install button and accept the license
-   Review all the pre-installation checks. You should be able to
    proceed with some PHP recommendations in red, but ONLY those, any
    other red check MUST be fixed before proceeding.
-   Fill in all the information required and continue
    -   you will need a MySQL user with access to a database that may
        exist or not, if it doesn't exist you will also need a MySQL
        user with enough permission to create a database

&lt;WRAP center round important 60%&gt; If the database exists it
**MUST** be empty, the install procedure DOES NOT migrate, there is a
migration procedure available if necessary. &lt;/WRAP&gt;

      * you can choose the password for the only user that will be created.

<img src="/en/corebosinstall02.png" class="align-center" width="800" />

-   now wait for all the installation work to be done
-   if all goes well you should receive a verification page welcoming
    you to the application
-   press the **Finish** button to reach the login page
-   **execute the database changes**, this is done using the **[coreBOS
    Updater](/en/devel/corebosupdater)**, which is a module that will
    take care of managing all the updates from now on. It will read the
    set of changes that need to be done and will permit you to apply
    them and undo some of them.
    -   login to the application as the admin user and go to the
        "**coreBOS Updater**" module.
    -   click on the **Get Updates** button
    -   go back to the list view and click on the **Apply All** button

&lt;WRAP center round important 80%&gt; For additional security it is
recommended that you take two more steps:

1.  Configure a [Basic
    Authentication](https://wiki.apache.org/httpd/PasswordBasicAuth)
    password protection on the application
2.  Delete all unused files. You can launch the **bettersafe.sh** script
    and also remember to eliminate the install and migration scripts and
    directory which have been renamed during the install process
3.  the **bettersafe.sh** will also **set the config.inc.php file to
    read-only** which is a very good idea even if you don't want to
    execute bettersafe

&lt;/WRAP&gt;

&lt;WRAP center round box 60%&gt; **Now comes all the fun**

-   Configure the application
-   Import your data
-   Create users

&lt;/WRAP&gt;

FAQ
---

~~QNA~~

??? I installed in windows but the Popup screen is empty.

!!! XAMMP configures your PHP to load files only from a couple of
directories. By default it does not look for files in the current
directory which is something that coreBOS depends upon. You must edit
your php.ini file, look for the include\_path directive and add the
current directory. Something like this;

    include_path = ".;C:\php\pear;C:\wamp\www"

What I usually do when I have to install on windows is edit
config.inc.php and add this line towards the end:

    echo get_include_path();

then I edit the php.ini directive putting the same value and adding the
current directory (.)

??? I have problems installing/recovering the database

!!! apply this change in my.cnf `max_allowed_packet = 16M`
<https://discussions.corebos.org/showthread.php?tid=1550>
