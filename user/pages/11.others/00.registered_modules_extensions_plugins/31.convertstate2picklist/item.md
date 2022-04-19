---
title: 'Convert State field to picklist'
---

Convert State field to picklist
===============================

This change will convert state fields on Accounts, Contacts, Vendors,
Leads and Inventory modules into shared picklists.

<embed src="/en/extensions/extensions/convertstate2picklist.zip" class="align-center" />

The changeset contains two state CSV files, one for US and one for
Spain. You must define which one to apply editing the changeset BEFORE
applying it. You will find the code in the

    build/changeSets/imported/convertState2Picklist.php

file and you must set the $importLang variable accordingly. You will
also find the two state files in the same directory and you can add your
own state files for your country by simply adding a new file and setting
the language extension accordingly.

You must import this change using the import button that you will find
on the coreBOS Updater list view.

&lt;WRAP center round alert 80%&gt; There is no support for undoing this
change yet. It wouldn't be difficult to undo so reach out if you need
that. &lt;/WRAP&gt;

---- dataentry ---- name : convertState2Picklist type : change
description\_wiki: This change will convert state fields on Accounts,
Contacts, Vendors, Leads and Inventory modules into shared picklists.
keywords\_tags : inventory, state, picklist, Account, Contact, Vendor,
Lead version : 1.0 homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:convertstate2picklist>
release\_dt : 2018-01-26 license : VPL price: 0 buyemail\_mail:
paypal(at)tsolucio(dot)com distribution: Free authorname : JPL TSolucio,
S.L. authoremail\_mail :info(at)tsolucio(dot)com authorhomepage\_url :
<http://tsolucio.com> supportemail\_mail :info(at)tsolucio(dot)com

------------------------------------------------------------------------
