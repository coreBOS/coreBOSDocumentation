---
title: 'Use of OpenOffice with Data inside the Application'
---

Use of OpenOffice with Data inside the Application
==================================================

This is the OpenOffice, LibreOffice + Rich Text Format merge feature for
coreBOS

Usage:
------

Create a template file using OpenOffice or LibreOffice. As placeholders
for the fields in coreBOS use the name of the entity followed by the
name of the field without any spaces and in capital letters, for
example: ACCOUNT\_ACCOUNTNAME will be replaced with the real account
name being merged.

These templates can only have **one record per template**. We have an
advanced merge extension which has this capability and much more.

Multi-line address (or descriptions or any field) are not supported by
the merge extension due to the way it manipulates the internal structure
of the document. To overcome this limitation we have introduced a small
workaround whereas we will replace the newline characters for two
exclamations (!!), then in the merged document you will have to convert
these two symbols back to newlines. To help with this task we ![include
two macros that do the work for you](/es/user/libreofficemacros.macro).
You will have to add the OpenOffice BASIC macros included in the project
to your word processor.

&lt;WRAP center round info 60%&gt; You can also get the file from the
build/oo-merge directory &lt;/WRAP&gt;

![An example template (.odt)](/es/user/oo_test_template.odt) is included
and can also be found in the build/oo-merge directory. The template uses
some labels as an example.

Login with a user with administrative rights.

Go to Settings-&gt;Mail Merge and load an OpenOffice or LibreOffice
(.odt) or Rich Text Format (.rtf) template for a specific module.

The supported modules are Leads, HelpDesk, Accounts, Contacts.

Go to a specific module, select one or more items (e.g. one or more
Contacts), choose the correct template in the 'Select template to Mail
Merge:' combobox and click the 'Merge' button.

Label Printing
--------------

![imprimir\_etiquetas](/page>es/imprimir_etiquetas)

Translation
-----------

In file: modules/Settings/language/xx\_yy.lang.php, cange line

    'LBL_DOC_MSWORD'=>'File has to be a Document of type doc/msword',

to

    'LBL_DOC_MSWORD'=>'File has to be a Document of type doc/msword, or OpenOffice/odt or Rich Text Format/rtf',

In file: include/language/xx\_yy.lang.php, add line:

    'DownloadMergeFile'=>'Download merged document'

&lt;WRAP center round important 75%&gt; **THIS IS IMPORTANT** if you
don't add the translation string to your language file you will not be
able to download the file. &lt;/WRAP&gt;

History
-------

    *[Joe] Installed by default in coreBOS
    *[Joe] Version 5.4.0 Updated for compatibility with vtiger 5.4.0
    *[Joe] Version 5.3.0 Updated for compatibility with vtiger 5.3.0
    *The multiline address field support has been added by Peter A. Gebhardt (casati)
    *Version 5.2.1 Updated for compatibility with vtiger 5.2.1
    *The fix for the html special chars has been provided by xweber on the vtiger forums.
    *The code for the utf8 escape sequences in rtf files has been taken from http://sourceforge.net/projects/phprtf
    *Version 5.1.0 Fixes problems with html special chars &,<,>,... for OpenOffice documents and supports utf8 chars in rtf documents.
    *This extension was born from a forum thread which had code for 4.2, JPL TSolucio, S.L. (Joe Bordes) ported it and maintains it with the Help of StudioSynthesis and other community members. Special mention to Peter A. Gebhardt (casati) who helped in the upgrade to 5.3.0.