---
title: 'pre-CRUD filters'
metadata:
    description: 'There are four filters that are launched on each of the Create, Retrieve, Update and Delete actions.'
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
        - event
    tag:
        - hooks
        - save
---

There are four filters that are launched on each of the Create, Retrieve, Update and Delete actions.

===

### corebos.filter.preSaveCheck

Filter launched before starting the Save process. Will receive, the $_REQUEST variable and the current object trying to be saved. It must return, besides these two input parameters, an error status, an error message, an error action and an array of variables to return to the edit screen the process was initiated from.

You can find [an example of this filter in the Documents module,](https://github.com/tsolucio/corebos/blob/master/modules/Documents/Documents.php#L180) where it checks if the attachment was correctly uploaded and aborts the save if it wasn't. 

<div class="notices blue"> Note that, in this example, the application has overridden the preSave method instead of registering an event. In the end, the result is the same.
</div>

### corebos.filter.preEditCheck

Filter launched before starting the Edit process. Will receive, the $_REQUEST variable, the Smarty object and the current object trying to be edited.

You can find [an example of this filter in the Payment module,](https://github.com/tsolucio/corebos/blob/master/modules/CobroPago/CobroPago.php#L506) where it checks if the record can be edited or not.

<div class="notices blue"> Note that, in this example, the application has overridden the preEdit method instead of registering an event. In the end, the result is the same.
</div>

### corebos.filter.preViewCheck

Filter launched before starting the Detail View process. Will receive, the $_REQUEST variable, the Smarty object and the current object trying to be viewed.

The next code will use this event to show a message on the DetailView of each record depending on the parity of its record ID.

First, we create a script that will receive the event and do the desired work.

**preViewCheck_msgIfCRMIDiseven**

```php 
class preViewCheck_msgIfCRMIDiseven extends VTEventHandler {
	private $_moduleCache = array();
 
	/**
	 * @param $handlerType
	 * @param $entityData VTEntityData
	 */
	public function handleEvent($handlerType, $entityData) {
	}
 
	public function handleFilter($handlerType, $parameter) {
		global $currentModule;
		if ($handlerType == 'corebos.filter.preViewCheck') {
				// $parameter is the QueryGenerator Object
				$request = $parameter[0];
				$smarty = $parameter[1];
				$focus = $parameter[2];
				if ($focus->column_fields['record_id'] % 2 == 0) {
					$smarty->assign('ERROR_MESSAGE_CLASS', 'cb-alert-success');
					$smarty->assign('ERROR_MESSAGE', 'CRMID is EVEN!');
				} else {
					$smarty->assign('ERROR_MESSAGE_CLASS', 'cb-alert-info');
					$smarty->assign('ERROR_MESSAGE', 'CRMID is ODD!');
				}
		}
		return $parameter;
	}
}
```
Next we register the event

```php 
include 'vtlib/Vtiger/Module.php';
require_once('include/events/include.inc');
$em = new VTEventsManager($adb);
$event = 'corebos.filter.preViewCheck';
$em->registerHandler($event, 'preViewCheck_msgIfCRMIDiseven.php', 'preViewCheck_msgIfCRMIDiseven');
echo "<h4>Event $event registered.</h4>";
```
The result looks like this:

![](crmidevenodd.png?width=100%)

### corebos.filter.preDeleteCheck

Filter launched before deleting a record. Will receive, the current object trying to be deleted and must return a boolean indicating if the action may proceed or not and a message to show in case it cannot.


