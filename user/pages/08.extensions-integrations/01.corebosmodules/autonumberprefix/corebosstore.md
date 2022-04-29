---
title: 'Auto Increment Number Field module'
---

Auto Increment Number Field module
==================================

This configuration module permits you to define different increment
counters with a prefix for fields in modules and then apply them with
conditions using workflows. It will permit you to have various
counter/increment fields on any module or increment differently the same
field depending on values in the record being saved.  
---- dataentry ---- name : tsolucio/AutoNumberPrefix type :
corebos-module description\_wiki : This configuration module permits you
to define different increment counters with a prefix for fields in
modules and then apply them with conditions using workflows. It will
permit you to have various counter/increment fields on any module or
increment differently the same field depending on values in the record
being saved. keywords\_tags : autoincrement, identifier, field,
settings, customnumber,counter version : 1.0 homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:autonumberprefix>
release\_dt : 2015-11-02 licenses : Vizsage price : 120eur
buyemail\_mail : paypal(at)tsolucio(dot)com distribution : Sale
authorname : JPL TSolucio, S.L. authoremail\_mail :
info(at)tsolucio(dot)com supportemail\_mail : info(at)tsolucio(dot)com

------------------------------------------------------------------------

  

Configuration
=============

You can create as many "counter" records as you need. They are created
in the module's interface as any other record in any other module. The
important fields are:

<table>
<thead>
<tr class="header">
<th>Field</th>
<th>Type</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Prefix</td>
<td>string</td>
<td>This is the text prefix that will be added to the start of the identifier. It is totally equivalent to the text prefix you can find in the default autonumbering in <strong>Settings</strong>. It may be left empty.</td>
</tr>
<tr class="even">
<td>Module</td>
<td>module multi-list</td>
<td>This is the module that the counter is for.</td>
</tr>
<tr class="odd">
<td>Format</td>
<td>string</td>
<td><a href="/en/extensions/extensions/autonumberprefix#number_formatting">see below</a></td>
</tr>
<tr class="even">
<td>Workflow Expression</td>
<td>checkbox</td>
<td>Indicates if the Format field contains a Workflow Expression that needs to be evaluated.</td>
</tr>
<tr class="odd">
<td>Active</td>
<td>checkbox</td>
<td>Indicates if the counter is active or not. Any record marked as inactive will not be used by the extension.</td>
</tr>
<tr class="even">
<td>Current Value</td>
<td>number</td>
<td>This is the current maximum value of the counter.</td>
</tr>
<tr class="odd">
<td>Default</td>
<td>checkbox</td>
<td>If more than one counter can be applied, the one marked as default will be used.</td>
</tr>
</tbody>
</table>

Install
-------

Once you have installed the module normally using module manager, you
will see that it adds a new function to the workflow system:

**AutoNumberInc(ANPid)**

You can now use this function in an Update Field workflow task to assign
the next counter value to any field based on any condition in the
module.

<img src="/en/extensions/extensions/autoincmodule/anpwf.png" class="align-center" />

The **ANPid** number is the internal CRMID of the record or the value of
the Increment field you want to use for the sequence. This number can be
found by looking in the URL of the Detail View of the record.

<img src="/en/extensions/extensions/autoincmodule/anpid.png" class="align-center" />

Number formatting
-----------------

The format field accepts three forms:

1.- Number  
A string of numbers that indicate both the number of characters and the
actual counter that must appear in the result. This is the same as the
default behavior you can find in the autonumber in **Settings**. For
example, with 000001 you will get the sequence:

000001, 000002,..., 000022, 000023, ...000101,...010001.... always with
6 numbers in the counter

2.- Date/Number  
An advanced format that accepts any [PHP supported date conversion
letter](http://php.net/manual/en/function.date.php) and the special
string **%u** for the number.

The string **%u** accepts the [PHP sprintf
format](http://php.net/manual/en/function.sprintf.php). So to obtain the
same sequence as in point 1 above you would use:

    %'.06u

If you want to put the current year followed by the previous 6 number
format you would use:

    Y-\%'.06\u

which would produce the sequence:

2015-000001, 2015-000002,..., 2015-000022, 2015-000023,
...2015-000101,...2015-010001....

3.- Workflow Expression

If you activate the "Workflow Expression" checkbox then we will parse
the format string through sprintf in order to put the correct number in
place and then pass the result to the workflow expression engine with
the context of the record triggering the workflow. This will permit you
to use any of the workflow expression functions to construct complex
formatting combinations.

For example, you could have an expression like

    concat(format_date('y'), '-', duedate)

or

    concat(duedate, '-%'.06u')

This is a real example from a coreBOS install:

    concat(format_date(get_date('now'),'ym'), '_', $(code_shop : (cbShop) code_shop) , '_%'.04u')

Fields
======

### Auto Number Prefix Information

<table>
<thead>
<tr class="header">
<th>Field</th>
<th>Type</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Auto Number Prefix No</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
</tr>
<tr class="even">
<td>Prefix</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>Module</td>
<td>module multi-list</td>
<td></td>
</tr>
<tr class="even">
<td>Format</td>
<td>string</td>
<td></td>
</tr>
<tr class="odd">
<td>Workflow Expression</td>
<td>checkbox</td>
<td></td>
</tr>
<tr class="even">
<td>Active</td>
<td>checkbox</td>
<td></td>
</tr>
<tr class="odd">
<td>Current Value</td>
<td>number</td>
<td></td>
</tr>
<tr class="even">
<td>Default</td>
<td>checkbox</td>
<td></td>
</tr>
<tr class="odd">
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
<tr class="even">
<td>Created Time</td>
<td>datetime</td>
<td></td>
</tr>
<tr class="odd">
<td>Modified Time</td>
<td>datetime</td>
<td></td>
</tr>
</tbody>
</table>

### Description

<table>
<thead>
<tr class="header">
<th>Field</th>
<th>Type</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Description</td>
<td>text</td>
<td></td>
</tr>
</tbody>
</table>
