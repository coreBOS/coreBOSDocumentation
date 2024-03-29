---
title: 'Users Authentication'
metadata:
    description: 'Types of Logos.'
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
        - authentication
    tag:
        - role
        - rbac
        - user
---

## SQL Database Authentication

coreBOS validates user access using a password hash saved in the database. The password can be changed by the user and also by users with administration rights. The password can be configured to automatically expire activating the scheduled task to do so and setting the number of days to expire the password with the global variable **Application_ExpirePasswordAfterDays**

This is the default behavior of the application called **SQL** mode, but there are various other ways of giving access to your users.

## LDAP Authentication
### Requirements

-  coreBOS installed
-  LDAP server should be installed and accessible by coreBOS.
-  You will need to have **php-ldap extension** installed on your server.

### Configuration
-  Set the global variable **User_AuthenticationType to LDAP** for the user
-  Configure the LDAP support in modules/Users/authTypes/config.ldap.php

<div class="notices red">
Remember that LDAP is only for authorizing, the user must exist in both applications.
</div>

### Query

If the default **User_AuthenticationType** is set to LDAP or AD (Active Directory), then on the create user screen you will have a Query Button.

![](createuserquery.png?width=100%)

Enter the LDAP username you would like to query and click on the "Query LDAP" button. This will retrieve the users information from LDAP and automatically fill up the user fields.

![](createuserfillin.png?width=100%)

Fill up any missing mandatory fields and click on the save button to create the user. Once created, you can log in using the username and LDAP password. The password for the user will be picked from LDAP which means that changes in LDAP password would reflect in the application without any changes.

## Active Directory Authentication
### Requirements

-  coreBOS installed
-  Active Directory server should be installed and accessible by coreBOS.
-  You will need to have **php-ldap extension** installed on your server.

### Configuration

-  Set the global variable **User_AuthenticationType** to **AD** for the user
-  Configure the Active Directory support directly in the adLDAP.php class (ugh!). Just open and customize the settings for your needs. The following settings match those needed for a 2012R2 Active Directory.

```php
...
class adLDAP {
 
    /**
     * Define the different types of account in AD
     */
    const ADLDAP_NORMAL_ACCOUNT = 805306368;
    const ADLDAP_WORKSTATION_TRUST = 805306369;
    const ADLDAP_INTERDOMAIN_TRUST = 805306370;
    const ADLDAP_SECURITY_GLOBAL_GROUP = 268435456;
    const ADLDAP_DISTRIBUTION_GROUP = 268435457;
    const ADLDAP_SECURITY_LOCAL_GROUP = 536870912;
    const ADLDAP_DISTRIBUTION_LOCAL_GROUP = 536870913;
    const ADLDAP_FOLDER = 'OU';
    const ADLDAP_CONTAINER = 'CN';
 
    /**
    * The default port for LDAP non-SSL connections
    */
    const ADLDAP_LDAP_PORT = '389';
    /**
    * The default port for LDAPS SSL connections
    */
    const ADLDAP_LDAPS_PORT = '636';
 
    /**
    * The account suffix for your domain, can be set when the class is invoked
    *
    * @var string
    */
        protected $accountSuffix = "@cortoso.com";
 
    /**
    * The base dn for your domain
    *
    * If this is set to null then adLDAP will attempt to obtain this automatically from the rootDSE
    *
    * @var string
    */
        protected $baseDn = "";
 
    /**
    * Port used to talk to the domain controllers.
    *
    * @var int
    */
    protected $adPort = self::ADLDAP_LDAP_PORT;
    /**
    * Array of domain controllers. Specifiy multiple controllers if you
    * would like the class to balance the LDAP queries amongst multiple servers
    *
    * @var array
    */
    protected $domainControllers = array("dc01.cortoso.com", "dc02.cortoso.com");
 
    /**
    * Optional account with higher privileges for searching
    * This should be set to a domain admin account
    *
    * @var string
    * @var string
    */
    protected $adminUsername = "ldap-binduser";
    protected $adminPassword = "super-password";
 
    /**
    * AD does not return the primary group. http://support.microsoft.com/?kbid=321360
    * This tweak will resolve the real primary group.
    * Setting to false will fudge "Domain Users" and is much faster. Keep in mind though that if
    * someone's primary group is NOT domain users, this is obviously going to mess up the results
    *
    * @var bool
    */
        protected $realPrimaryGroup = false;
 
    /**
    * Use SSL (LDAPS), your server needs to be setup, please see
    * http://adldap.sourceforge.net/wiki/doku.php?id=ldap_over_ssl
    *
    * @var bool
    */
        protected $useSSL = false;
 
    /**
    * Use TLS
    * If you wish to use TLS you should ensure that $useSSL is set to false and vice-versa
    *
    * @var bool
    */
    protected $useTLS = true;
 
    /**
    * Use SSO
    * To indicate to adLDAP to reuse password set by the brower through NTLM or Kerberos
    *
    * @var bool
    */
    protected $useSSO = false;
 
    /**
    * When querying group memberships, do it recursively
    * eg. User Fred is a member of Group A, which is a member of Group B, which is a member of Group C
    * user_ingroup("Fred","C") will returns true with this option turned on, false if turned off
    *
    * @var bool
    */
        protected $recursiveGroups = true;
 
    ...
?>
```

-  configure multiple domain-controllers to prevent SPOFs
-  configured hostnames for your domain-controllers and common names in their SSL certificates have to match to prevent SSL trust errors
-  use TLS to ensure encrypted transport of user account data
-  create a special user for ldap binding, without any further permissions and with unlimited password validity (configure it in adLDAP with AdminUsername and AdminPassword parameters)

<div class="notices red">
Remember that Active Directory is only for authorizing, the user must exist in both applications.
</div>

## OpenLDAP Authentication

If you use SSL or TLS, it is absolutely necessary that your openldap trusts the domain controllers and their certificates. Make sure that you have a corporate certificate authority and issue certificates for all of your domain controllers. (Sounds horrible but is quite easy if you just install a Active Directory integrated certificate authority as Windows Server role.) You will need to export the certificate and import it for openssl.

### Export CA Certificate
Use Windows Certificate Mangement Console to export the CA certificate base-64 encoded. If you installed the ca web management feature, just visit:[http://your-dc/certsrv/certcarc.asp](http://your-dc/certsrv/certcarc.asp), choose base-64 format and click "Download CA certificate".

### Import CA Certificate for OpenLDAP

On RHEL-based systems OpenLDAP uses a default dir at /etc/openldap/certs to store trustable ca certificates in it. Just put the exported certificate file there.

Ensure that the path is configured in /etc/openldap/ldap.conf (RHEL) or /etc/ldap/ldap.conf (Debian). Either as file or folder. (Sometimes the folder configuration doesn’t work)

```
TLS_CACERT /etc/openldap/certs/cortoso-ca.cer
TLS_CACERTDIR /etc/openldap/certs/
```

## Test adLDAPTest adLDAP
### Ldapsearch

With **ldapsearch** you can test the functionality of encrypted LDAP e.g. by:

```
root@crm:~# ldapsearch -H "ldaps://dc01.cortoso.com" -b "" -s base -Omaxssf=0
SASL/EXTERNAL authentication started
ldap_sasl_interactive_bind_s: Unknown authentication method (-6)
  additional info: SASL(-4): no mechanism available:
```
TLS connection is established but we haven’t supplied authentication. OK so far. If you face any problems, add "-d7" to get some debugging output.

### PHP Testscript

To be able to test adLDAP, it is much easier to write a small php snippet than doing it directly with the application. You will find an adldap_test.php Helper Script file, in the same directory where adLDAP.php resides (modules/Users/authTypes).

Replace user and password for the user you want to test authentication and execute it on the command line:

```
php adldap_test.php
```
It should state success and output the username and mail address if available.

To make sure it is also working in Apache Webserver context, you may also open it in a browser or use curl to test it:

```
curl http://your_server/your_corebos/modules/Users/authTypes/adldap_test.php

```

## Notes and comments

-  All admin users will always authenticate in SQL mode (against the database)
-  You can set the authentication variable to any value for any user, effectively authenticating each one using different methods
-  Make sure the case for the user names match that of your coreBOS usernames
-  You cannot have spaces or special characters in the LDAP username as these are not supported by coreBOS.
-  LDAP and Active Directory features are based on the work of others (thanks!)
   -  [vtiger company](https://discussions.corebos.org/documentation/lib/exe/fetch.php?media=en:adminmanual:vtiger-ldap-integration-v1.0.pdf)
   -  [Marco at adminberlin.de](http://adminberlin.de/vtiger-crm-6-active-directory-authentication/)


## Two-Factor Authentication

coreBOS supports Two-Factor Authentication as of June 2017.

<div class="notices blue">
This functionality should work with LDAP and Active Directory
</div>

This functionality can be defined per user using global variables.

The global variables are:

-   **User_2FAAuthentication:** boolean 0 or 1 value that will activate the functionality
-   **User_2FAAuthentication_SendMethod:** SMS, EMAIL, or MOBILE as the system to send the code to the user. If the value is set to SMS, the application will search first for phone_work and then phone_mobile. SMS **MUST** be active and configured, if not the EMAIL method will be used. The code will be sent to the user's main email. Read below to find out how MOBILE works.


**MOBILE** expects you to have installed the [Google Authenticator App](https://play.google.com/store/apps/details?id=com.google.android.apps.authenticator2) on your mobile device. Then go to your users' profile and click on the "Two Factor Activation" button. This will take you to a screen where you can activate this functionality. Once activated you will see your secret code, both as a number and as a QRCode that can be scanned into the App.

![](2faactivation.png?width=100%)

Once that is done, you will be able to generate codes that will let you login on your cell phone.