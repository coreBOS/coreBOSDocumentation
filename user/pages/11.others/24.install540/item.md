---
title: 'Install coreBOS 5.4.0'
---

Install coreBOS 5.4.0
=====================

Requirements
------------

-   Apache 2.0.40 or above.
-   MySQL 5.1.x
-   PHP 5.3.x

&lt;WRAP center round info 75%&gt; This is a typical **WAMP/LAMP
stack**. All linux distributions have this natively so we recommend you
install the packages from your distribution (make sure you have the
right versions). On windows download the XAMPP stack from apache
friends. You can see the [list of application versions
here](http://code.stephenmorley.org/articles/xampp-version-history-apache-mysql-php).
You should download [version 1.7.7 from
sourceforge](http://sourceforge.net/projects/xampp/files/XAMPP%20Windows/1.7.7).
&lt;/WRAP&gt;

### MYSQL Requirements

Please make sure to review MySQL configuration (my.cnf or server start
parameters)

<table>
<tbody>
<tr class="odd">
<td>SQL_MODE</td>
<td>Should not have STRICT_TRANS_TABLE</td>
</tr>
<tr class="even">
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
<td></td>
</tr>
<tr class="even">
<td>OpenSSL</td>
<td>Optional</td>
<td>Imap with OpenSSL should be enabled in case Mail server needs to be connected via SSL</td>
</tr>
<tr class="odd">
<td>Curl</td>
<td>Optional</td>
<td></td>
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
<td>2000</td>
</tr>
<tr class="even">
<td>post_max_size</td>
<td>16M</td>
</tr>
<tr class="odd">
<td>memory_limit</td>
<td>512M</td>
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
</tbody>
</table>

&lt;WRAP center round info 75%&gt; If you have the PHP Suhosin extension
installed, this extension adds restrictions to make PHP more secure, but
some of these restrictions break coreBOS.

To solve this problem you must change two variables in the suhosin
config file: (normally: /etc/php5/conf/suhosin.ini)

    suhosin.post.max_vars = 2000
    suhosin.request.max_vars = 2000

After this you must restart your apache server. &lt;/WRAP&gt;

### File Permissions

Provide read-write access to the following files and folder
(recursively):

&lt;WRAP center round important 60%&gt; Read and Write permissions
should be enabled for user/group who owns webserver process (like
www-data or httpd or apache). &lt;/WRAP&gt;

    *config.inc.php 
    *tabdata.php 
    *install.php 
    *parent_tabdata.php 
    *cache 
    *cache/images/ 
    *cache/import/ 
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
    *test/wordtemplatedownload/ 
    *test/product/ 
    *test/user/ 
    *test/contact/ 
    *test/logo/ 
    *logs/ 
    *modules/Webmails/tmp/

&lt;WRAP center round important 60%&gt; Please make sure you meet all
these requirements &lt;/WRAP&gt;

Install
-------

-   Download the source code from GitHub
-   copy the code into a folder in accessible from your webserver
    install
-   type in the URL of the folder into your browser
-   you should get the **Configuration Wizard** welcome page

<img src="/en/corebosinstall01.png" class="align-center" width="800" />

-   click on the Install button and accept the license
-   Review all the pre installation checks. You should be able to
    proceed with some PHP recommendations in red, but ONLY those, any
    other red check MUST be fixed before proceeding.
-   Fill in all the information required and continue
    -   you will need a mysql user with access to a database that may
        exist or not, if it doesn't exist you will also need a mysql
        user with enough permission to create a database
    -   you can chose to load a set of example information and the
        password for the only user that will be created.

<img src="/en/corebosinstall02.png" class="align-center" width="800" />

-   next select the modules and languages you wish to have available by
    default in the application. You can install these and also
    deactivate them later, so don't worry too much about it.
-   now wait for all the installation work to be done
-   if all goes well you should receive a verification page welcoming
    you to the application
-   press the **Finish** button to reach the login page
