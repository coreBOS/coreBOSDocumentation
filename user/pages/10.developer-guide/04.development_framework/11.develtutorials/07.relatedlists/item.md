---
title: 'How to add related lists to a module'
metadata:
    description: 'How to add related lists to a module'
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
        - relatedlists
    tag:
        - howto
---

the TLDR; version is

- Relate with Documents &gt; get_attachments
- Relate with Calendar &gt; get_activities
- Relate with Emails &gt; get_emails
- Is custom relation &gt; whatever function you have implemented
- 1:m &gt; get_dependents_list
- m:m &gt; get_related_list

===

How to associate Standard Modules such as Accounts, Potentials & Vendors to a New module (Payslip) with m:m relation
--------------------------------------------------------------------------------------------------------------------

Through vtlib we can establish a relation between a standard module and a new one using the setRelatedList function:

```php
$accounts=Vtiger_Module::getInstance('Accounts');
$accounts->setRelatedList(Vtiger_Module::getInstance('Payslip'), 'header',Array('ADD','SELECT'))
```

this would establish a m:m relation between Accounts and Payslip so that a new section will appear in the more information tab of accounts and should just work.

You may have to add the 'header' label to the accounts language file.

This m:m relation is based on the `get_related_list` default function (no function name was given in the example call so `get_related_list` function is used by default) and the relation between accounts and payslip will be saved in the `vtiger_crmentityrel` database table.

This is vtlib 2.1 normal behavior.

How to associate Standard Modules such as Accounts, Potentials & Vendors to a New module (Payslip) with a 1:m relation. The old fashion way
-------------------------------------------------------------------------------------------------------------------------------------------

This works as follows: When you click on the +info tab of any entity, the code goes into the vtiger_relatedlist table in the database where the information of what is related is. It extracts from this table, the names of the related entities and the functions that need to be called to get the list of related entities. These functions will be called against the object representing the entity. For example,

```php
$accounts->setRelatedList(Vtiger_Module::getInstance('Payslip'), 'header',Array('ADD'),'get_payslip');
```

will create an entry in the vtiger_relatedlist indicating that the get_payslip() function should be called against an account object to get it's related payslips. That is why the function must be added in accounts. If you look in the vtiger_relatedlists table you will see that accounts is also related to contacts through the get_contacts function which can also be found in the accounts.php script.

So if we want to establish a new section in the +info tab based on a relation that is not standard (get_related_list()/vtiger_crmentityrel), we **COULD** create our own function inside that entity to retrieve the related elements based on the relation we have established.

So if we add a new field to the payslip module of uitype 10 to capture the related account. That means that we are forcing a 1:m relation, 1 account has m payslips, 1 payslip has one account (the one captured by the uitype 10 field). This means that the vtiger_payslip database table has a new field called accountid where the relation between the modules is being saved. As you see, the standard get_related_list() function will not find this relation as it knows nothing about the fields you have added (it looks for the relation in the vtiger_crmentityrel table), so we need to create our own new function that will retrieve the records based on this uitype 10 field.

The best way to do this is to copy an existing function from another module and modify the query, you really don't have to look at the other lines of the function, all the get_xxx functions are the same. You have to change:

- the name of the function, which has to be the same as the one you put in the setRelatedList() call
- the name of the function in the two debug lines at the beginning and end of function. This isn't needed for it to work but may come in handy if you ever have to debug the script.
- the query, to get the records you need

```sql
select vtiger_payslip.*, vtiger_crmentiy.*
from vtiger_payslip
inner join vtiger_crmentity.crmid=vtiger_payslip.payslpiid
left join vtiger_users...
left join vtiger_group...
...
where deleted=0 and vtiger_payslip.accountid = $id
```

In the case of the example a new get_payslip() function must be added to modules/Accounts/Accounts.php script

**NOTE**. This is the way to establish a **m:m relation** when you are not using the standard vtiger_crmentityrel table. For example, if you wanted to show the entities related to a document or an activity which use other tables to save their relations.

How to associate Standard Modules such as Accounts, Potentials & Vendors to a New module (Payslip) with a 1:m relation. The new vtlib way
-----------------------------------------------------------------------------------------------------------------------------------------

With vtlib we can now establish this relation easily. All we have to do is add a uitype 10 capture field in the module with the 1 relation and the use the special function get_dependents_list() to retrieve the related entities. So if we add a new field to the payslip module of uitype 10 to capture the related account. That means that we are forcing a 1:m relation, 1 account has m payslips, 1 payslip has one account (the one captured by the uitype 10 field). This means that the vtiger_payslip database table has a new field called accountid where the relation between the modules is being saved. Now all we have to do is relate the account's payslips with the setRelatedList function:

```php
$accounts->setRelatedList(Vtiger_Module::getInstance('Payslip'), 'header',Array('ADD'),'get_dependents_list');
```

This is the correct way of establishing this relation. We will also get an "Add" button on top of the related list that will preselect the related entity automatically.

How to associate new modules with Activities – Add To Do / Add Event
--------------------------------------------------------------------

To associate any module to Activities you cannot use the standard get_related function.

When you use the function setRelatedList(relatedmodule, header, actions, function) and you don't specify the callback function, a generic get_related_list function is called. This function expects to find a many to many relation in the vtiger_crementityrel table.

Activities does not establish it's relation in the vtiger_crmentityrel table, but in others, so you can't use the standard function, you have to use the get_activities function.

Activities is done like this:

```php
setRelatedList(relatedmodule, header, actions, 'get_activities')
```

**BUT**, that means that your new module **MUST** have this function in it's main file. You can do two things:

- copy the get_activities function from Accounts.php into data/CRMEntity.php, this way you will have it for all your modules
- copy the get_activities function from Accounts.php into your new module's main file. This will make your module distributable and easier to upgrade

You don't have to make any modifications to the get_activities function, it is the same for all modules. Which of the two choices depends on the goal of the new module and the changes you are making.

How to associate new modules with Documents
-------------------------------------------

To associate any module to Documents you cannot use the standard get_related function.

When you use the function setRelatedList(relatedmodule, header, actions, function) and you don't specify the callback function, a generic get_related_list function is called. This function expects to find a many to many relation in the vtiger_crementityrel table.

Documents does not establish it's relation in the vtiger_crmentityrel table, but in others, so you can't use the standard function, you have to use the get_attachments function.

Documents is done like this:

```php
setRelatedList(relatedmodule, header, actions, 'get_attachments')
```

How to associate new modules with Activities History
----------------------------------------------------

Similar to the above solution in this case you must use the already existing coreBOS functions to achieve an event history.

Create a new related block:

```php
setRelatedList('Calendar', 'Activity History', 'add', 'get_history')
```

Now copy the get_history function from Accounts.php (for example) and adapt accordingly (normally just change Accounts for your module)


Adding a related list to an existing module without modifying it's code
-----------------------------------------------------------------------

Since November 2014 the application has a way of adding related lists to a module without having to modify its main class. [Read all about it on the hooks wiki page!](../20.corebos_hooks)

Frequently Asked Questions
--------------------------

<div class="notices blue">
<h2>Why doesn't get_dependents_list support the SELECT button? </h2>
</div>

select is directly eliminated in get_dependents_list because that action is dangerous and not supported

think about it

a get_dependents_list is a 1:N relation, so on the related list, you are seeing those records that have a certain ID in their uitype 10. If I am on an Account, and looking at the contacts related list, I am seeing those contacts that have that accountid in their field. Select would mean that we would have to **overwrite** that value for the selected records, effectively **UNRELATING** them from the records they are related to now. **That is dangerous** and probably NOT what the user wants to do.

If it IS what you want to do you have to go to the module (contacts in the example above) filter and mass edit the accountid field. So you can "select" if you want, but you have to do it through mass edit. It must be a conscious and intentional act, not an unintentional one.

> "ah, I thought it worked like the other select not that it was going to trash all my relations!"
