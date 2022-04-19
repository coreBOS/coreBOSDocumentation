---
title: 'coreBOS 5.4.0 to coreBOS 5.5.0 Changes'
---

coreBOS 5.4.0 to coreBOS 5.5.0 Changes
======================================

Comments on important changes
-----------------------------

This release is all about three things:

1.  **PHP 5.4 and 5.5 support and code cleanup.** coreBOS now runs
    correctly on PHP 5.4 and PHP 5.5. Besides fixing the code we have
    started upgrading the libraries and documenting the dependencies and
    are relentlessly hunting down all the notice and warning messages
    (we have eliminated hundreds already).
2.  **REST enhancements: [Customer
    Portal](http://corebos.org/documentation/doku.php?id=en:devel:coreboscp).**
    from coreBOS 5.5 forward we have a whole new set of webservice
    functionality to support advanced application development like our
    [coreBOSCP Customer Portal
    Project](http://corebos.org/documentation/doku.php?id=en:devel:coreboscp)
    and many others.
3.  **[Code changes](/en/devel/packagemodules) and
    [updates](/en/devel/corebosupdater) enhancements**. A whole new
    distribution method that will make future upgrades, both in the code
    and in the database MUCH easier. This prepares us to start launching
    the new functionality we have right around the corner.

There are a few more important features that are worth detailing next
and all the changes can be found below with full details on the tickets,
some even have their own wiki page with an additional explanation, this
is just a quick relation of the work done in this release.

### Code Cleanup

re-branding, adapting, code cleanup and structure, bug fixes, more
user-friendly error messages, getting rid of warnings and notice
messages

### PHP 5.4 and 5.5 Support. Upgrade libraries

    *Improve compatibility with PHP5.4/5.5
    * update phpmailer library to 5.2.7 and centralize mail sending and some additional library updates and study

### Document module enhancements

custom fields on documents, related list of entities visible on
documents

### Import Enhancements

-   Sequence numbering for autoincrement fields not respected on import
-   Import with merge and default value. Thanks boris\_fr
-   When importing with merge fields selected, these fields do not
    always appear in selectable mapping
-   Enhance import to search related fields on any field

### Report Enhancements

-   support for A4 on PDF export
-   Enable basic reporting on Emails
-   Reporting on SalesOrder related entities:
    ('Accounts','Contacts','Potentials','Quotes') and Invoice related
    entity Contact

### Other Enhancements

-   translation enhancements in Settings
-   Forecast field and workflow on potential
-   clean and optimize database
-   better email validation: ~~issue:175~~: Please enter a valid Email:
    use angularjs/chrome email validation regular expression to fix
    issues with firefox and certain email formats

### REST Enhancements

-   ~~issue:195~~, ~~issue:196~~: REST enhancements for better UPDATE
    and not lose product lines on inventory modules update
-   fixes ~~issue:184~~: Webservices Calendar sets/returns only 1
    contact id and no custom field information
-   security enhancements on REST global search: related to issue
    ~~issue:157~~
-   fixes ~~issue:164~~: REST Enhancement: Document manipulation|
-   fixes ~~issue:162~~, ~~issue:163~~: REST Enhancement: method to
    Recover Password, 163: REST Enhancement: method to validate if a
    given user has portal access
-   fixes ~~issue:161~~: REST Enhancement: get filter fields
-   fixes ~~issue:160~~: REST Enhancement: get translation
-   fixes ~~issue:162~~, ~~issue:163~~: REST Enhancement: method to
    Recover Password, 163: REST Enhancement: method to validate if a
    given user has portal access
-   fixes ~~issue:161~~: REST Enhancement: get filter fields
-   fixes ~~issue:60~~: REST Enhancement: get translation
-   fixes ~~issue:159~~: REST Enhancement: add Ticket FAQ comment
-   fixes ~~issue:150~~, fixes ~~issue:151~~, fixes ~~issue:152~~, fixes
    ~~issue:153~~, fixes ~~issue:154~~, fixes ~~issue:155~~, fixes
    ~~issue:156~~, fixes ~~issue:157~~, fixes ~~issue:158~~: REST
    Enhancements for coreBOSCustomer Portal
-   branding: eliminate vtiger reference
-   fixes ~~issue:127~~: Enhance REST query language to support related
    entities
-   standard system to install webservice methods:
    InstallRESTChanges.php and registerWSAPI()
-   fixes ~~issue:126~~: Establish basic relations with other modules
    when creating a record via REST
-   fixes ~~issue:124~~: get PDF output of inventory modules through
    REST
-   fixes ~~issue:123~~: Enhance field information returned from REST
    interface
-   fixes ~~issue:120~~: speed optimizations for REST

### Repackaging and Structure

-   [Restructure package directories](/en/devel/packagemodules) to make
    it easier to distribute changes
-   [coreBOS Updater](/en/devel/corebosupdater) to make it easy to
    distribute changes and updates to the system
-   Create build directory for development
-   Enhance Package Export to re-package in different ways. Add support
    for exporting Language packs.

Full list of changes from GIT commits
-------------------------------------

<table>
<tbody>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/3a10b4b">3a10b4b</a></td>
<td>delete some additional files catched while testing upgrade to 5.5</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/a2479fc">a2479fc</a></td>
<td>fixes for 5.5 upgrade: new methods to update version in file and database. code cleanup and branding</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/154a859">154a859</a></td>
<td>no postgreSQL support on install</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/9362188">9362188</a></td>
<td>eliminate empty help reference during install</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/ad80bbc">ad80bbc</a></td>
<td>migration changes to 5.5</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/129cb7d">129cb7d</a></td>
<td>eliminate select modules step in install</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/d6087af">d6087af</a></td>
<td>branding calendar export and deleting install image that is not needed</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/fef3f93">fef3f93</a></td>
<td>testing and fixing install for 5.5 release</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/0909414">0909414</a></td>
<td>fixes ~~issue:195~~, ~~issue:196~~: REST enhancements for better UPDATE and not lose product lines on inventory modules</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/7cee73d">7cee73d</a></td>
<td>related to issue ~~issue:118~~: update freetag for Tag Cloud functionality</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/23d73b5">23d73b5</a></td>
<td>fixes ~~issue:119~~: Fix the rules export/import and now the groups export/import is supported</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/65605c0">65605c0</a></td>
<td>cbupdater: controled update error. make cleandb more robust</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/6518f66">6518f66</a></td>
<td>fixes ~~issue:140~~: clean and optimize database from updater</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/cc9c271">cc9c271</a></td>
<td>Reporting on SalesOrder related entities: ('Accounts','Contacts','Potentials','Quotes') and Invoice related entity Contact</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/916ac74">916ac74</a></td>
<td>delete workflow method in cbupdater: fix PotentialForecast update</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/6a8568a">6a8568a</a></td>
<td>fix inherted incorrect mass replace of vtiger_files, vtiger_headers and vtiger_users</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/ccc086a">ccc086a</a></td>
<td>syntax error in message</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/d419465">d419465</a></td>
<td>Forcast field and workflow on potential</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/6484509">6484509</a></td>
<td>Enable basic reporting on Emails</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/04e8702">04e8702</a></td>
<td>elminate notice, related to issue ~~issue:144~~</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/bf25d37">bf25d37</a></td>
<td>new installer frontend</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/1c96a91">1c96a91</a></td>
<td>support for A4 on PDF report export</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/18caea8">18caea8</a></td>
<td>Merge pull request #4 from playmono/patch-2</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/77405a6">77405a6</a></td>
<td>Update EditViewUtils.php</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/8a7bae0">8a7bae0</a></td>
<td>translating enhancements on settings</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/e958485">e958485</a></td>
<td>add notescf, document custom field table, just in case</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/64b7a39">64b7a39</a></td>
<td>security enhancements in inventory module: picked up from VT6</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/f0ac1cc">f0ac1cc</a></td>
<td>fixes ~~issue:88~~: Lead Convert Field Mapping header formatting when editing</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/dc1a105">dc1a105</a></td>
<td>Simpler package installation from manifest.xml</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/7b011ff">7b011ff</a></td>
<td>fixes ~~issue:175~~: Please enter a valid Email: use angularjs/chrome email validation regular expression to fix issues with firefox and certain email formats</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/e55b229">e55b229</a></td>
<td>squashing warning and notices: related to issue ~~issue:144~~</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/2b41cc7">2b41cc7</a></td>
<td>debuging upgrade to 5.5</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/e8facf6">e8facf6</a></td>
<td>additional helper methods for cbupdater</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/230f0ed">230f0ed</a></td>
<td>database changes for 5.5 release</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/980530e">980530e</a></td>
<td>cbupdater: coreBOS updater module</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/1e9c12d">1e9c12d</a></td>
<td>squashing warnings. related to issue ~~issue:144~~</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/0cf3222">0cf3222</a></td>
<td>squash another warning. related to issue ~~issue:144~~</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/648deff">648deff</a></td>
<td>fixes ~~issue:135~~: When adding a filter rule trough Vtlib, the rule does'nt exist in Vtiger: update vtlib filter to group condition support</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/1671759">1671759</a></td>
<td>fixes ~~issue:187~~: create method to import module manifest file</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/197c965">197c965</a></td>
<td>fix syntax error in users curreny field name</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/50a5459">50a5459</a></td>
<td>branding and code cleanup</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/33c33af">33c33af</a></td>
<td>code cleanup and eliminating warning messages. related to issue ~~issue:144~~</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/b3897ce">b3897ce</a></td>
<td>fix error in language export and add English en_us to module manager</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/d5f1fba">d5f1fba</a></td>
<td>fixes ~~issue:184~~: Webservices Calendar sets/returns only 1 contact id and no custom field information</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/27ef3bf">27ef3bf</a></td>
<td>fixes ~~issue:106~~: Fix error when concat queries, a space is needed</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/04a4f21">04a4f21</a></td>
<td>fixes issue ~~issue:181~~: error inserting modtracker link on detail view action list</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/fdb51b4">fdb51b4</a></td>
<td>related to ~~issue:144~~: getting rid of warnings and messages</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/4e687aa">4e687aa</a></td>
<td>Fix warning in php_writeexcel</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/5821985">5821985</a></td>
<td>fix syntax error in webserive error message</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/82c9d0c">82c9d0c</a></td>
<td>Root entries in .gitignore</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/b4a0162">b4a0162</a></td>
<td>Fix inventory totals in workflows, bug ~~issue:121~~</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/d0bb412">d0bb412</a></td>
<td><a href="http://trac.vtiger.com/cgi-bin/trac.cgi/ticket/7399">http://trac.vtiger.com/cgi-bin/trac.cgi/ticket/7399</a></td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/6db1806">6db1806</a></td>
<td>fixes ~~issue:179~~: When importing with merge fields selected, these fields do not always appear in selectable mapping</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/17dc68d">17dc68d</a></td>
<td>related to issue ~~issue:144~~: eliminate warnings and notice on install</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/aac005d">aac005d</a></td>
<td>fixes ~~issue:178~~: Account capture on contact overwrites addres without confirmation =&gt; now we ask</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/6fddb9d">6fddb9d</a></td>
<td>fixes ~~issue:177~~: Data in the Department field is being truncated</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/0068c9e">0068c9e</a></td>
<td>fixes ~~issue:177~~: Data in the Department field is being truncated</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/2f5ccc7">2f5ccc7</a></td>
<td>related to issue ~~issue:144~~: eliminate warnings and notice</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/9712b05">9712b05</a></td>
<td>custom fields on documents, related list of entities visible on documents</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/12b31ca">12b31ca</a></td>
<td>translating workflow strings</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/4fa21fa">4fa21fa</a></td>
<td>fixes ~~issue:173~~: ticket fixed</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/c95b5e5">c95b5e5</a></td>
<td>issue ~~issue:112~~: path to send generated reports change and not send attachements</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/faae3c5">faae3c5</a></td>
<td>fixes ~~issue:172~~: add SSL/TLS support on outgoing email server</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/2b84781">2b84781</a></td>
<td>Fix the filters in Calendar when use conditions with custom fiedls.</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/4459c99">4459c99</a></td>
<td>related to issue ~~issue:118~~: update phpmailer library to 5.2.7 and centralize mail sending</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/ac0f4eb">ac0f4eb</a></td>
<td>fixes ~~issue:170~~: Error translating labels in Home Module Widget. Minor speed/memory optimization</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/12975ee">12975ee</a></td>
<td>fixes ~~issue:169~~: Sequence numbering for autoincrement fields not respected on import</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/945df35">945df35</a></td>
<td>eliminate backup files</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/973c95c">973c95c</a></td>
<td>fixes ~~issue:168~~: Error breaking up text line in email</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/690fa60">690fa60</a></td>
<td>eliminate warnings in package import: Thanks Adam Heinz (trac 7476). Related to issue ~~issue:144~~.</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/26cf68e">26cf68e</a></td>
<td>better error message when we cant find file</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/a050246">a050246</a></td>
<td>fixes ~~issue:165~~: workflow formula expressions with major and minor signs. some minor code cleanup</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/df5a39c">df5a39c</a></td>
<td>fixes ~~issue:139~~: Import with merge and default value. Thanks boris_fr</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/846cfb0">846cfb0</a></td>
<td>code cleanup and structure</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/51ea7ba">51ea7ba</a></td>
<td>testing document REST enhancements: restructure attachments for future email support</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/6df535c">6df535c</a></td>
<td>security enhancements on REST global search: related to issue ~~issue:157~~</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/fb01ba4">fb01ba4</a></td>
<td>fixes ~~issue:164~~: REST Enhancement: Document manipulation</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/1ecaa94">1ecaa94</a></td>
<td>fixes ~~issue:162~~, ~~issue:163~~: REST Enhancement: method to Recover Password, 163: REST Enhancement: method to validate if a given user has portal access</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/44e0dae">44e0dae</a></td>
<td>fixes ~~issue:161~~: REST Enhancement: get filter fields</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/1bbd234">1bbd234</a></td>
<td>fixes ~~issue:160~~: REST Enhancement: get translation</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/756c47d">756c47d</a></td>
<td>fixes ~~issue:60~~: REST Enhancement: get translation</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/039ad18">039ad18</a></td>
<td>fixes ~~issue:159~~: REST Enhancement: add Ticket FAQ comment</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/913e528">913e528</a></td>
<td>fixes ~~issue:150~~, fixes ~~issue:151~~, fixes ~~issue:152~~, fixes ~~issue:153~~, fixes ~~issue:154~~, fixes ~~issue:155~~, fixes ~~issue:156~~, fixes ~~issue:157~~, fixes ~~issue:158~~: REST Enhancements for coreBOSCustomer Portal</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/8af4a37">8af4a37</a></td>
<td>branding: eliminate vtiger reference</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/b5a234b">b5a234b</a></td>
<td>fixes ~~issue:149~~: Workflow CRUD does not work on servers configured with wildcard domains</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/e03dd8d">e03dd8d</a></td>
<td>fixes ~~issue:147~~: All documents are getting attached to email sent from Mail Manager</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/8cbca7f">8cbca7f</a></td>
<td>fixes ~~issue:146~~: Incorrect use or translation of LBL_NOTE</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/c25a0bd">c25a0bd</a></td>
<td>fixes ~~issue:143~~: Warning message when creating new contact in contact image field</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/cfe61ad">cfe61ad</a></td>
<td>missing changes for Mass Edit on Search patch: Thanks to Paul Lefevre for that catch</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/3efaf3e">3efaf3e</a></td>
<td>fixes ~~issue:137~~: cannot empty asterisk extension in user preferences</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/4cb178d">4cb178d</a></td>
<td>simply format the code so we can read it and try to enhance it</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/35ef908">35ef908</a></td>
<td>update packages to be in sync with file changes. fix error in pack.sh for bundle packages</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/950a89b">950a89b</a></td>
<td>fix language export by adding dependencies information and update Spanish package which had it missing</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/c9f8726">c9f8726</a></td>
<td>fixes ~~issue:134~~: Invoice Module - Cannot select a contact name with an apostrophe</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/e766cfb">e766cfb</a></td>
<td>fixes ~~issue:133~~: Workflows and Custom Fields</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/21f1038">21f1038</a></td>
<td>fixes ~~issue:112~~: Update Import.zip with the new change</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/2136c52">2136c52</a></td>
<td>fixes ~~issue:112~~: Change Mailer to send_mail in runScheduledImport</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/ab508da">ab508da</a></td>
<td>issue ~~issue:112~~: I forgot to delete VtigerMailer object that now not used</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/1ba46d6">1ba46d6</a></td>
<td>issue ~~issue:112~~: Change Mailer to send mail in Scheduler Reports</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/7aef523">7aef523</a></td>
<td>Convert currency fields in workflows, fixes ~~issue:121~~</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/84aa27a">84aa27a</a></td>
<td>fixes ~~issue:131~~: mass edit support for product taxes and unit price</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/c9de157">c9de157</a></td>
<td>fixes 131: mass edit support for product taxes and unit price</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/e8fe4d5">e8fe4d5</a></td>
<td>add some more security into customer portal code</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/8c4a361">8c4a361</a></td>
<td>fixes ~~issue:128~~: error message saving company information</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/b02660a">b02660a</a></td>
<td>Fix special characters in comment productlines when cron RecurringInvoice.service is execute</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/df11817">df11817</a></td>
<td>fixes ~~issue:115~~: update Import zip with the new functionality</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/e7a8700">e7a8700</a></td>
<td>fixes ~~issue:127~~: Enhance REST query language to support related entities</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/68d1d25">68d1d25</a></td>
<td>standard system to install webservice methods: InstallRESTChanges.php and registerWSAPI()</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/064fbb4">064fbb4</a></td>
<td>Error to show Sen Notification in Calendar, always showed No by a translation error.</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/475f8bf">475f8bf</a></td>
<td>Fix the problem to download Documents with coma</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/121f3eb">121f3eb</a></td>
<td>fixes ~~issue:126~~: Establish basic relations with other modules when creating a record via REST</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/01f89e1">01f89e1</a></td>
<td>fixes ~~issue:125~~: Some REST enhancements and bug fixes</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/c4710a1">c4710a1</a></td>
<td>fixes ~~issue:124~~: get PDF output of inventory modules through REST</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/6bc2f22">6bc2f22</a></td>
<td>fixes 124: get PDF output of inventory modules through REST</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/1e7cd01">1e7cd01</a></td>
<td>fixes ~~issue:123~~: Enhance field information returned from REST interface</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/b6b297e">b6b297e</a></td>
<td>fixes ~~issue:120~~: speed optimizations for REST</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/362f25b">362f25b</a></td>
<td>fixes ~~issue:106~~: Control if we have columnstotal or not in secondary module query to add inventoryproductrel fields</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/20120dd">20120dd</a></td>
<td>code cleanup</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/39a1f66">39a1f66</a></td>
<td>Restructure package directory Create build directory for developement Enhance Package Export to re-package in different ways Add support for exporting Language packs export scripts in build</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/96ae446">96ae446</a></td>
<td>cambios encontrados al repasar migración a git</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/a803cce">a803cce</a></td>
<td>Improve compatibility with PHP5.4/5.5, fixes ~~issue:109~~</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/302ae47">302ae47</a></td>
<td>Fixed translation label on installation</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/1bb738f">1bb738f</a></td>
<td>Changed default database name on installation</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/086969f">086969f</a></td>
<td>fix error attaching files when sending direct emails and only send emails to active users. gitkeep for empty directories</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/f101636">f101636</a></td>
<td>Add missing empty directories from vtiger CRM 5.4.0 GA</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/82c0334">82c0334</a></td>
<td>fixes ~~issue:115~~: Enhance import to search related fields on any field</td>
</tr>
<tr class="odd">
<td><a href="https://github.com/tsolucio/corebos/commit/895b4e7">895b4e7</a></td>
<td>fixes ~~issue:114~~: optional and mandatory packages versioned</td>
</tr>
<tr class="even">
<td><a href="https://github.com/tsolucio/corebos/commit/cc3d0cc">cc3d0cc</a></td>
<td>Create README.md</td>
</tr>
</tbody>
</table>
