---
title: 'How to filter records on a module based on menu parameter'
metadata:
    description: 'Filtering modules.'
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
    tag:
        - filter
        - howto
---

Sometimes we put in one module two or more similar concepts; products we sell and products we buy, accounts we work with and accounts that are partners, quotes for clients and template quotes,... and also different categories, for example, tickets of different company departments.

===

We can easily filter these on the module. Using the custom filter functionality we can create filters to show the different concepts being saved in the same module, but sometimes, we want to take this a step further and simulate the existence of a real separation without having to create two or more custom modules (which is also a very good alternative).

To accomplish this logical separation of physical records living on the same table we have to add some custom programming on our module to detect the category the user is looking for and force the condition onto the SQL that retrieves the records.

First we have to create a menu entry that indicates what the user is going to see and pass in, on the URL, some indicator of what we want to filter. Then we have to save that information somewhere so it gets passed around for an event handler to access it and modify the query accordingly. It actually is that easy, just three steps, but there is one caveat that we have to avoid. Let's see how to do this with a real example.

I am going to separate the Account module records. In one category we will show all accounts that live in Australia, on the other we will show all the other accounts.

The condition we are going to add to the query is:

***bill_country='Australia'***

or

***bill_country!='Australia'***

We create two menu URL entries:

<table class="table table-striped">
<th>Accounts from Australia</th>
<td>index.php?action=index&amp;module=Accounts&amp;filterAustralia=Australia</td>
</tr>
<tbody>
<tr class="odd">
<th>Accounts not from Australia</th>
<td>index.php?action=index&amp;module=Accounts&amp;filterAustralia=</td>
</tr>
</tbody>
</table>

Now we register the event handler and create a script to modify the query. The event is:

[corebos.filter.listview.querygenerator.before](../../11.develtutorials/20.corebos_hooks/item.md#corebosfilterlistviewquerygeneratorbefore)

and our handler script will be **modules/Accounts/FilterAustralia.php**

The code to register the event is

```php
<?php
// Turn on debugging level
$Vtiger_Utils_Log = true;
include_once('vtlib/Vtiger/Module.php');
require_once('include/events/include.inc');
global $adb;

function registerEvent($event) {
    global $adb;
    $em = new VTEventsManager($adb);
    $em->registerHandler($event, 'modules/Accounts/FilterAustralia.php', 'AccountFilterAustraliaHandler');
    echo "<h4>Event $event registered.</h4>";
}

registerEvent('corebos.filter.listview.querygenerator.before');

echo '</body></html>';
?>
```

And the handler looks like this

```php
class AccountFilterAustraliaHandler extends VTEventHandler {
    private $_moduleCache = array();

    /**
     * @param $handlerType
     * @param $entityData VTEntityData
     */
    public function handleEvent($handlerType, $entityData) {
    }

    public function handleFilter($handlerType, $parameter) {
        global $currentModule;
        if ($currentModule=='Accounts') {
            switch($handlerType) {
                case 'corebos.filter.listview.querygenerator.before':
                    // $parameter is the QueryGenerator Object
                    if (isset($_REQUEST['filterAustralia']) and $_REQUEST['filterAustralia']=='Australia') {
                        $parameter->addCondition('bill_country','Australia','e','and');
                    } else {
                        $parameter->addCondition('bill_country','Australia','n','and');
                    }
                    break;
            }
        }
        return $parameter;
    }
}
```

Notice how we check for the variable coming in on the URL from the menu. If you try this at this point you will see that you actually get the filtered records when you first access the module from each menu entrance, but you will also see that it all gets lost as soon as you do any other action. This is because the filter variable is only present on the menu URL, when we navigate to some other part of the application this filter variable is not being passed along. So our first hurdle is to pass the information around. This is easy to do using the PHP session variables. Since session variables are per application and available to each PHP script always all we need to do is load the filter on to a session variable. We do this in **modules/Accounts/ListView.php** and it looks like this

```php
<?php
if (isset($_REQUEST['filterAustralia'])) {
    coreBOS_Session::set('AccountsFilterAustralia', $_REQUEST['filterAustralia']);
}
include_once('modules/Vtiger/ListView.php');
?>
```

With this change our event handler now looks like this

```php
class AccountFilterAustraliaHandler extends VTEventHandler {
    private $_moduleCache = array();

    /**
     * @param $handlerType
     * @param $entityData VTEntityData
     */
    public function handleEvent($handlerType, $entityData) {
    }

    public function handleFilter($handlerType, $parameter) {
        global $currentModule;
        if ($currentModule=='Accounts') {
            switch($handlerType) {
                case 'corebos.filter.listview.querygenerator.before':
                    // $parameter is the QueryGenerator Object
                    if (isset($_SESSION['AccountsFilterAustralia']) and $_SESSION['AccountsFilterAustralia']=='Australia') {
                        $parameter->addCondition('bill_country','Australia','e','and');
                    } else {
                        $parameter->addCondition('bill_country','Australia','n','and');
                    }
                    break;
            }
        }
        return $parameter;
    }
}
```

and we can navigate anywhere we want and even search inside the filtered record set with no problem. As soon as we go to the menu and access the other category the filter value changes and we see the other set of records.

Now this is all fine and dandy until the user decides to open a new tab in the browser. It turns out that the session variables are application based, so the new tab inherits all the values (which is why you don't have to login again on the new tab). When the user goes to accounts he sees the records filtered depending on the menu entry selected, which is correct but if it is different then the menu option selected in the first tab the session variable is overwritten and now any action taken on the first tab will load the set of records selected on the second tab instead of respecting the set selected there. In other words the filter is browser based, not tab based and that just isn't right. We need some way to detect the tab we are on and put the filter variable in the session based on the tab: **coreBOS to the rescue!!**

coreBOS has a browser variable called **corebos\_browsertabID** which identifies the tab it is in and it sends that information in to PHP on every call to the backend as a cookie. This variable can be used freely by any programmer both in JavaScript and PHP.

The application itself does not use this variable but in the case we are trying to solve in this article it is exactly what we need. We save the filter variable coming from the menu in a session variable marked with the browser tab identifier and we are done.

The final version of our modifications looks like this:

**modules/Accounts/FilterAustralia.php**

```php
class AccountFilterAustraliaHandler extends VTEventHandler {
    private $_moduleCache = array();

    /**
     * @param $handlerType
     * @param $entityData VTEntityData
     */
    public function handleEvent($handlerType, $entityData) {
    }

    public function handleFilter($handlerType, $parameter) {
        global $currentModule;
        if ($currentModule=='Accounts') {
            switch($handlerType) {
                case 'corebos.filter.listview.querygenerator.before':
                    // $parameter is the QueryGenerator Object
                    if (isset($_SESSION['AccountsFilterAustralia'.$_COOKIE['corebos_browsertabID']]) and $_SESSION['AccountsFilterAustralia'.$_COOKIE['corebos_browsertabID']]=='Australia') {
                        $parameter->addCondition('bill_country','Australia','e','and');
                    } else {
                        $parameter->addCondition('bill_country','Australia','n','and');
                    }
                    break;
            }
        }
        return $parameter;
    }
}
```

**modules/Accounts/ListView.php**

```php
<?php
if (isset($_REQUEST['filterAustralia'])) {
    coreBOS_Session::set('AccountsFilterAustralia'.$_COOKIE['corebos_browsertabID'], $_REQUEST['filterAustralia']);
}
include_once('modules/Vtiger/ListView.php');
?>
```

**Enjoy the power of a system that helps you help your users!!**

[Download the code.](filteraustralia.zip)
