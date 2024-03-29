---
title: 'Application Standard Message Output'
metadata:
    description: 'Application Standard Message Output'
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
        - standardoutputmessage
    tag:
        -howto
---

coreBOS gives the developer a standard way of sending messages to the user in detail and edit view. The styling is based on Lighting Design.

===

You activate the message by settings the Smarty **ERROR\_MESSAGE\_CLASS** and **ERROR\_MESSAGE** template variables.

The next script will output a message in each supported class:

```php
<?php
include_once('vtlib/Vtiger/Module.php');
require_once('Smarty_setup.php');
$smarty = new vtigerCRM_Smarty();
$smarty->assign('APP', $app_strings);
$smarty->assign('ERROR_MESSAGE_CLASS', 'cb-alert-warning');
$smarty->assign('ERROR_MESSAGE', 'This is a WARNING message.');
$smarty->display('applicationmessage.tpl');
$smarty->assign('ERROR_MESSAGE_CLASS', 'cb-alert-danger');
$smarty->assign('ERROR_MESSAGE', 'This is a DANGER message.');
$smarty->display('applicationmessage.tpl');
$smarty->assign('ERROR_MESSAGE_CLASS', 'cb-alert-info');
$smarty->assign('ERROR_MESSAGE', 'This is an INFO message.');
$smarty->display('applicationmessage.tpl');
$smarty->assign('ERROR_MESSAGE_CLASS', 'cb-alert-success');
$smarty->assign('ERROR_MESSAGE', 'This is a SUCESS message.');
$smarty->display('applicationmessage.tpl');
$smarty->assign('OPERATION_MESSAGE', 'This is a special operation NOT permitted message.');
$smarty->display('modules/Vtiger/OperationNotPermitted.tpl');
?>
```

Copy the script to any module and call it directly. For example, create a script:

modules/Accounts/showAppMsg.php

copy the contents above inside and save. Now go to your browser and type in:

```
http://YOUR_SERVER/YOUR_coreBOS/index.php?module=Accounts&action=showAppMsg
```