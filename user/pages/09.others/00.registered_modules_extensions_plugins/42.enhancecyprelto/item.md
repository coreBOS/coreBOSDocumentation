---
title: 'Separate Account and Contact field on Payments'
---

Separate Account and Contact field on Payments
==============================================

This enhancement, which is coreBOS Updater compatible and does not
modify any base files, will extract the Account from the RelatedTo field
on the Payment module and create a new Account field.

&lt;WRAP center round important 60%&gt; It will NOT copy any existing
values. It just creates the new field. &lt;/WRAP&gt;

Then it will add an event controller to set the value of the new account
field when we create a payment record from the related list of a
contact.

---- dataentry ---- name : SeparateACCyP type : enhancement
description\_wiki: This enhancement will add a new Account field on the
Payments module. keywords\_tags : Payments, CobroPago, RelatedTo,
separate, Account, Contact version : 1.0 homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:enhancecyprelto>
release\_dt : 2015-06-20 license : Vizsage price: 25eur buyemail\_mail:
paypal(at)tsolucio(dot)com distribution: Sale authorname : JPL TSolucio,
S.L. authoremail\_mail :info(at)tsolucio(dot)com authorhomepage\_url :
<http://tsolucio.com> supportemail\_mail :info(at)tsolucio(dot)com

------------------------------------------------------------------------
