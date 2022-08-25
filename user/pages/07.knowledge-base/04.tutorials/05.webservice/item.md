---
title: 'Web Service Documentation'
metadata:
    description: 'Menu Editor'
    author: 'Eleni Kullira'
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
        - howto
---

---

## Web Service Documentation

### Global Search

Global search, unlike the search button located on each module, searches all modules in coreBOS. By default, Global Search will search the entire system. Currently, Global Search is able to search for accounts, potentials, leads, documents and other modules within the system.

#### getSearchResults -Operation

The operation you need for the simple global search

GET URL Format :

```
http://144.91.100.102:8880/corebos/webservice.php?operation
=getSearchResults&sessionName={{sessionName}}&query=lin
&serch_onlyin=&restrictionids={"userId":"module_rest_idxrecordid",
"accountId":"module_rest_idxrecordid","contactId":"module_rest_idxrecordid"}
```

**Query parameters**
<div class="alpha right"></div>
|Key | Value | Description|
|--- | --- | ---|
|operation | getSearchResults | The operation you need for the simple global search|
|sessionName | {{sessionName}} | The value of a hashing value that you need to connect to coreBOS.|
|query | lind | The word that you are searching for|
|serch_onlyin | Comma-separated list of module names | The module(s) that you want to search in. If the field is empty you are searching at all modules|
|restrictionids | {"userId":"module_rest_idx0", "accountId":"module_rest_idx0" "contactId":"module_rest_idx0"} | The id of the user and the id of the the records in some modules. If userid is given, the search will be executed as that user, with that user’s permissions. If accountid and/or contactid are given, the records returned must be related to those records.|
<br> 

**SessionName**
<br> 
```
var hash = CryptoJS.MD5(token+accesskey).toString();
```

**Response: This is a PHP Serialized object.**

```json
{
    "success": true,
    "result": "a:7:{i:0;a:10:{s:7:\"Lead No\";s:5:\"LEA74\";s:9:\"Last Name\";s:7:\"Lindall\";s:10:\"First Name\";s:9:\"Carmelina\";s:7:\"Company\" ;s:29:\"George Jessop Carter Jewelers\";s:5:\"Phone\";s:12:\"303-724-7371\";s:7:\"Website\ ";s:43:\"http://www.georgejessopcarterjewelers.co...\";s:5:\"Email\";s:29:\"carmelina_lindall@lindall.com\" ;s:11:\"Assigned To\";s:9:\"Var Group\";s:2:\"id\";s:7:\"10x4242\";s:18:\"search_module_name\";s:5: \"Leads\";}i:1;a:10:{s:7:\"Lead No\";s:6:\"LEA133\";s:9:\"Last Name\";s:7:\"Dilello\";s:10: \"First Name\";s:7:\"Lindsey\";s:7:\"Company\";s:23:\"Biltmore Investors Bank\";s:5: \"Phone\";s:12:\"909-639-9887\";s:7:\"Website\";s:36:\"http://www.biltmoreinvestorsbank.com\";s:5:\"Email\";s:27:\"lindsey.dilello@hotmail.com\";s:11:\"Assigned To\";s:9: \"Var Group\";s:2:\"id\";s:7:\"10x4301\";s:18:\"search_module_name\";s:5: \"Leads\";}i:2;a:10:{s:7:\"Lead No\";s:6:\"LEA107\";s:9:\"Last Name\";s:7:\"Hochard\";s:10:\"First Name\";s:7: \"Malinda\";s:7:\"Company\";s:23:\"Logan Memorial Hospital\";s:5:\"Phone\";s:12:\"317-722-5066\";s:7:\"Website\";s:36: \"http://www.loganmemorialhospital.com\";s:5:\"Email\";s:25: \"malinda.hochard@yahoo.com\";s:11:\"Assigned To\";s:9:\"Var Group\";s:2:\"id\";s:7:\"10x4275\";s:18: \"search_module_name\";s:5:\"Leads\";}i:3;a:7:{s:9:\"Vendor No\";s:5:\"VEN66\";s:11: \"Vendor Name\";s:29:\"George Jessop Carter Jewelers\";s:5:\"Phone\";s:12:\"303-724-7371\";s:5: \"Email\";s:29:\"carmelina_lindall@lindall.com\";s:8:\"Category\";s:0:\"\";s:2:\"id\";s:6: \"2x2281\";s:18:\"search_module_name\";s:7:\"Vendors\";}i:4;a:7:{s:9:\"Vendor No\";s:6:\"VEN259\";s:11: \"Vendor Name\";s:20:\"Bogart, Edward J Esq\";s:5:\"Phone\";s:12:\"604-458-2387\";s:5: \"Email\";s:18:\"bkazar@hotmail.com\";s:8:\"Category\";s:0:\"\";s:2:\"id\";s:6:\"2x2474\";s:18: "search_module_name\";s:7:\"Vendors\";}i:5;a:7:{s:22:\"Project Milestone Name\";s:15: \"Belinda Mathius\";s:14:\"Milestone Date\";s:10:\"2016-04-13\";s:11:\"description\";s:43: \"fringilla ornare placerat, orci lacus ve...\";s:12:\"Created Time\";s:19:\"2015-06-09 10:57:17\";s:13: \"Modified Time\";s:19:\"2016-05-16 15:48:10\";s:2:\"id\";s:7:\"31x8826\";s:18: \"search_module_name\";s:16:\"ProjectMilestone\";}i:6;a:7:{s:22:\"Project Milestone Name\";s:14: \"Howard Lindley\";s:14:\"Milestone Date\";s:10:\"2016-04-25\";s:11:\"description\";s:43: \"In mi pede, nonummy ut, molestie in, tem...\";s:12:\"Created Time\";s:19: \"2015-06-15 09:22:55\";s:13:\"Modified Time\";s:19:\"2015-07-10 13:41:29\";s:2:\"id\";s:7:\"31x9385\";s:18: \"search_module_name\";s:16:\"ProjectMilestone\";}}"
}
```


#### getSearchResultsArray-Operation

The operation you  need for the global search where the response is in the form of an array.

**GET URL Format :**

```
http://144.91.100.102:8880/corebos/webservice.php?operation=getSearchResultsArray&sessionName={{sessionName}}&query=lin&serch_onlyin= &restrictionids={"userId":"module_rest_idxrecordid","accountId":"module_rest_idxrecordid","contactId":"module_rest_idxrecordid"}
```

**Query parameters**

<div class="alpha right"></div>

|Key | Value | Description|
|--- | --- | ---|
|operation | getSearchResultsArray | The operation you  need for the global search where the response is in the form of an array.|
|sessionName | {{sessionName}} | The value of a hashing value that you need to connect to coreBOS.|
|query | lind | The word that you are searching for|
|serch_onlyin |  | The module that you want to search in. If the field is empty you are searching at all modules|
|restrictionids | {"userId":"module_rest_idx0", "accountId":"module_rest_idx0", "contactId":"module_rest_idx0"} | The id of the user and the id of the the records in some modules|

<br> 

**SessionName**
<br> 
```
var hash = CryptoJS.MD5(token+accesskey).toString();
```

**Response**

```json
{
    "success": true,
    "result": [
        {
            "Lead No": "LEA74",
            "Last Name": "Lindall",
            "First Name": "Carmelina",
            "Company": "George Jessop Carter Jewelers",
            "Phone": "303-724-7371",
            "Website": "http://www.georgejessopcarterjewelers.co...",
            "Email": "carmelina_lindall@lindall.com",
            "Assigned To": "Var Group",
            "id": "10x4242",
            "search_module_name": "Leads"
        },
        {
            "Lead No": "LEA133",
            "Last Name": "Dilello",
            "First Name": "Lindsey",
            "Company": "Biltmore Investors Bank",
            "Phone": "909-639-9887",
            "Website": "http://www.biltmoreinvestorsbank.com",
            "Email": "lindsey.dilello@hotmail.com",
            "Assigned To": "Var Group",
            "id": "10x4301",
            "search_module_name": "Leads"
        },
        {
            "Lead No": "LEA107",
            "Last Name": "Hochard",
            "First Name": "Malinda",
            "Company": "Logan Memorial Hospital",
            "Phone": "317-722-5066",
            "Website": "http://www.loganmemorialhospital.com",
            "Email": "malinda.hochard@yahoo.com",
            "Assigned To": "Var Group",
            "id": "10x4275",
            "search_module_name": "Leads"
        },
        {
            "Vendor No": "VEN66",
            "Vendor Name": "George Jessop Carter Jewelers",
            "Phone": "303-724-7371",
            "Email": "carmelina_lindall@lindall.com",
            "Category": "",
            "id": "2x2281",
            "search_module_name": "Vendors"
        },
        {
            "Vendor No": "VEN259",
            "Vendor Name": "Bogart, Edward J Esq",
            "Phone": "604-458-2387",
            "Email": "bkazar@hotmail.com",
            "Category": "",
            "id": "2x2474",
            "search_module_name": "Vendors"
        },
        {
            "Project Milestone Name": "Belinda Mathius",
            "Milestone Date": "2016-04-13",
            "description": "fringilla ornare placerat, orci lacus ve...",
            "Created Time": "2015-06-09 10:57:17",
            "Modified Time": "2016-05-16 15:48:10",
            "id": "31x8826",
            "search_module_name": "ProjectMilestone"
        },
        {
            "Project Milestone Name": "Howard Lindley",
            "Milestone Date": "2016-04-25",
            "description": "In mi pede, nonummy ut, molestie in, tem...",
            "Created Time": "2015-06-15 09:22:55",
            "Modified Time": "2015-07-10 13:41:29",
            "id": "31x9385",
            "search_module_name": "ProjectMilestone"
        }
    ]
}
```

#### getSearchResultsArrayWithTotals-Operation

The operation you need for global search where the response is in the form of an array, with the total count that the word appears in each module.

**GET URL Format :**

```
http://144.91.100.102:8880/corebos/webservice.php?operation=getSearchResultsArrayWithTotals&sessionName={{sessionName}}&query=lin&serch_onlyin= &restrictionids={"userId":"module_rest_idxrecordid","accountId":"module_rest_idxrecordid","contactId":"module_rest_idxrecordid"}
```

**Query parameters**

<div class="alpha right"></div>

|Key | Value | Description|
|--- | --- | ---|
|operation | getSearchResultsArrayWithTotals | The operation you need for global search where the response is in the form of an array, with the total count that the word appears in each module.|
|sessionName | {{sessionName}} | The value of a hashing value that you need to connect to coreBOS.|
|query | lind | The word that you are searching for|
|serch_onlyin |  | The module that you want to search in. If the field is empty you are searching at all modules|
|restrictionids | {"userId":"module_rest_idx0", "accountId" :"module_rest_idx0", "contactId":"module_rest_idx0"} | The id of the user and the id of the the records in some modules|
<br> 

**SessionName** 
<br> 
```
var hash = CryptoJS.MD5(token+accesskey).toString();
```


**Response**

```json
{
    "success": true,
    "result": {
        "records": [
            {
                "Lead No": "LEA74",
                "Last Name": "Lindall",
                "First Name": "Carmelina",
                "Company": "George Jessop Carter Jewelers",
                "Phone": "303-724-7371",
                "Website": "http://www.georgejessopcarterjewelers.co...",
                "Email": "carmelina_lindall@lindall.com",
                "Assigned To": "Var Group",
                "id": "10x4242",
                "search_module_name": "Leads"
            },
            {
                "Lead No": "LEA133",
                "Last Name": "Dilello",
                "First Name": "Lindsey",
                "Company": "Biltmore Investors Bank",
                "Phone": "909-639-9887",
                "Website": "http://www.biltmoreinvestorsbank.com",
                "Email": "lindsey.dilello@hotmail.com",
                "Assigned To": "Var Group",
                "id": "10x4301",
                "search_module_name": "Leads"
            },
            {
                "Lead No": "LEA107",
                "Last Name": "Hochard",
                "First Name": "Malinda",
                "Company": "Logan Memorial Hospital",
                "Phone": "317-722-5066",
                "Website": "http://www.loganmemorialhospital.com",
                "Email": "malinda.hochard@yahoo.com",
                "Assigned To": "Var Group",
                "id": "10x4275",
                "search_module_name": "Leads"
            },
            {
                "Vendor No": "VEN66",
                "Vendor Name": "George Jessop Carter Jewelers",
                "Phone": "303-724-7371",
                "Email": "carmelina_lindall@lindall.com",
                "Category": "",
                "id": "2x2281",
                "search_module_name": "Vendors"
            },
            {
                "Vendor No": "VEN259",
                "Vendor Name": "Bogart, Edward J Esq",
                "Phone": "604-458-2387",
                "Email": "bkazar@hotmail.com",
                "Category": "",
                "id": "2x2474",
                "search_module_name": "Vendors"
            },
            {
                "Project Milestone Name": "Belinda Mathius",
                "Milestone Date": "2016-04-13",
                "description": "fringilla ornare placerat, orci lacus ve...",
                "Created Time": "2015-06-09 10:57:17",
                "Modified Time": "2016-05-16 15:48:10",
                "id": "31x8826",
                "search_module_name": "ProjectMilestone"
            },
            {
                "Project Milestone Name": "Howard Lindley",
                "Milestone Date": "2016-04-25",
                "description": "In mi pede, nonummy ut, molestie in, tem...",
                "Created Time": "2015-06-15 09:22:55",
                "Modified Time": "2015-07-10 13:41:29",
                "id": "31x9385",
                "search_module_name": "ProjectMilestone"
            }
        ],
        "totals": {
            "Accounts": 0,
            "Leads": 3,
            "Contacts": 0,
            "Potentials": 0,
            "Campaigns": 0,
            "HelpDesk": 0,
            "Products": 0,
            "Documents": 0,
            "Emails": 0,
            "Faq": 0,
            "Vendors": 2,
            "PriceBooks": 0,
            "Quotes": 0,
            "PurchaseOrder": 0,
            "SalesOrder": 0,
            "Invoice": 0,
            "ServiceContracts": 0,
            "Services": 0,
            "CobroPago": 0,
            "Assets": 0,
            "ModComments": 0,
            "ProjectMilestone": 2,
            "ProjectTask": 0,
            "Project": 0,
            "InventoryDetails": 0,
            "cbTermConditions": 0,
            "cbCalendar": 0,
            "cbSurvey": 0,
            "cbSurveyQuestion": 0,
            "cbSurveyDone": 0,
            "cbSurveyAnswer": 0,
            "cbCompany": 0,
            "cbQuestion": 0,
            "ProductComponent": 0,
            "Messages": 0,
            "cbPulse": 0,
            "MsgTemplate": 0,
            "cbCredentials": 0,
            "Timecontrol": 0,
            "cbBCase": 0,
            "DocumentFolders": 0,
            "pricebookproductrel": 0,
            "AutoNumberPrefix": 0,
            "ProcessLog": 0,
            "cbProcessAlert": 0,
            "cbProcessFlow": 0,
            "cbProcessStep": 0
        }
    }
}
```

### Workflows, Rules, Questions and Actions
#### ExecuteWorkflow-Operation 

[Workflows](../../../05.configuration-tools/10.workflow) are a very powerful part of the application. They permit us to automate our business logic to some extent making it possible to standardize process and have the application do some of the repetitive tasks our business requires. When you want to trigger a workflow, only from outside of the coreBOS,ie. from the portal or anywhere else and you don't have access to activate it from the corebos system, then it should be set to System Mass Actions .

**GET URL Format :**
```
http://144.91.100.102:8880/corebos/webservice.php?operation=ExecuteWorkflow&sessionName={{sessionName}}&workflow=46&entities=["module_rest_idx77"]
```

**Query parameters**

<div class="alpha right"></div>

|Key | Value | Description|
|--- | --- | ---|
|operation | ExecuteWorkflow | The operation you need to execute a workflow.|
|sessionName | {{sessionName}} | The value of a hashing value that you need to connect to coreBOS.|
|workflow | The workflow_id e.g. 46 | The workflow id that you want to trigger|
|entities | [module_id x record_id] e.g. [11x77] | The id of the module and the record that you want the workflow to be triggered|

**Response**
```json 
{
    "success": true,
    "result": true
}
```

If the response is “success:true” then the workflow has been triggered e.g if you trigger a update field workflow task the result will be :


The wf update field tasks :

![wf1](wf1.PNG?classes=max)

The account before the wf trigger:

![wf2](wf2.PNG?classes=max)

The account after the wf trigger:

![wf3](wf3.PNG?classes=max)


#### ExecuteWorkflowWithContext-Operation 

Basically you can execute a workflow from outside corebos using the ExecuteWorkflowWithContext operation, which allows you to include a new parameter named context. The value of the parameter context can be any set of workflow context variables that your workflow supports. So, if you are sending an email, it can be an id of a Message Template(MsgTemplate) record you need to send. What does that mean? Typically you will create a workflow with a Send Mail task, but you don't want to hardcode the mail template. You create the send mail task only to define the recepients, and cc of the mail, while the template is decided on the webservice request itself. Saying that, the send mail task will serve only as a placeholder for the real template defined in the ws request.
There is an extensive (and undocumented) list of context variables that permit tweaking the functionality of each workflow task.
The other parameters remain the same, you have to define the id of the workflow that you need to execute, the id of the record that you need that workflow to be executed towards, and as always the sessionName in order to authenticate.


**GET URL Format :**

```
http://144.91.100.102:8880/corebos/webservice.php?operation=ExecuteWorkflowWithContext&sessionName={{sessionName}}&workflow=43&entities=["module_rest_idx244623"]&context={"SendThisMsgTemplate":44127}
```

**Query parameters**
<div class="alpha right"></div>

|Key | Value | Description|
|--- | --- | ---|
|operation | ExecuteWorkflowWithContext | The operation you need to execute a workflow.|
|sessionName | {{sessionName}} | The value of a hashing value that you need to connect to coreBOS.|
|workflow | The workflow_id e.g. 43 | The workflow id that you want to trigger|
|entities | [module_id x record_id] e.g. ["module_rest_idx244623"] | The id of the module and the record that you want the workflow to be triggered|
|context | {"SendThisMsgTemplate":44127} | The context (message template) of the email that you want to send|

```json
Response 
{
    "success": true,
    "result": true
}
```

If the response is “success:true” then the workflow has been triggered e.g if you trigger a send mail workflow the result will be :


**The send mail tasks :**

![sendmail](sendmail1.PNG?classes=max)

**A message template that you want to send :**

![template](msgtemp.PNG?classes=max)

The email that has been sent have to be same with the context and no with th workflow send mail task:

![email](email.PNG?classes=max)

#### getBusinessActions-Operation

[Business Actions](../../../05.configuration-tools/03.business-actions) are things that can happen inside the application. They enhance the vtiger CRM link system and they can affect any part of the application

**GET URL Format :**

```
http://144.91.100.102:8880/corebos/webservice.php?operation=getBusinessActions&sessionName={{sessionName}}&view=ListView&module=Accounts&id=accounts_id&linktype=LISTVIEWBASIC
```

**Query parameters**
<div class="alpha right"></div>

|Key | Value | Description|
|--- | --- | ---|
|operation | getBusinessActions | The operation you  need to get the businessAction|
|sessionName | {{sessionName}} | The value of a hashing value that you need to connect to coreBOS.|
|view | ListView | The view that you want to show the result you get from the businessAction. The view can be : listview,detailsview, related module|
|module | Accounts | The module that you want to trigger the businessAction|
|id | e.g. 74 | The id of an account contact|
|linktype | LISTVIEWBASIC | The linktype you will use. You can use one of these linktypes: LISTVIEWBASIC, DETAILVIEWBASIC, HEADERSCRIPT, DETAILVIEWWIDGET|
<br> 

**SessionName**
<br> 
```
var hash = CryptoJS.MD5(token+accesskey).toString();
```

**Response**

```json
{
    "success": true,
    "result": {
        "LISTVIEWBASIC": [
            {
                "tabid": "6",
                "linkid": "43076",
                "linktype": "LISTVIEWBASIC",
                "linklabel": "Send SMS",
                "linkurl": "SMSNotifierCommon.displaySelectWizard(this, 'Accounts');",
                "linkicon": "",
                "sequence": "0",
                "status": false,
                "handler_path": "",
                "handler_class": "",
                "handler": "",
                "onlyonmymodule": "0"
            },
            {
                "tabid": "6",
                "linkid": "244610",
                "linktype": "LISTVIEWBASIC",
                "linklabel": "Generate Document",
                "linkurl": "javascript:showgendoctemplates('Accounts');",
                "linkicon": "",
                "sequence": "0",
                "status": false,
                "handler_path": "",
                "handler_class": "",
                "handler": "",
                "onlyonmymodule": "1"
            },
            {
                "tabid": "6",
                "linkid": "43152",
                "linktype": "LISTVIEWBASIC",
                "linklabel": "LBL_SEND_MAIL_BUTTON",
                "linkurl": "return eMail('Accounts',this);",
                "linkicon": "",
                "sequence": "0",
                "status": false,
                "handler_path": "",
                "handler_class": "",
                "handler": "",
                "onlyonmymodule": "0"
            },
            {
                "tabid": "6",
                "linkid": "43155",
                "linktype": "LISTVIEWBASIC",
                "linklabel": "LBL_MAILER_EXPORT",
                "linkurl": "return mailer_export();",
                "linkicon": "",
                "sequence": "0",
                "status": false,
                "handler_path": "",
                "handler_class": "",
                "handler": "",
                "onlyonmymodule": "0"
            }
        ]
    }
}
```

#### getBusinessAction - coreBOS Webservice Development
```json
<?php

//parameters
$params = "sessionName=$cbSessionID";
$params.= "&operation=getBusinessActions";
$params.= "&view=ListView";
$params.= "&module=Accounts";
$params.= "&id=74";
$params.= "&linktype=LISTVIEWBASIC";

//Retrieve must be GET Request.
$response = $httpc->fetch_url("$cbURL?$params");
$dmsg.= debugmsg("Raw response (json)", $response);

//decode the json encode response from the server.
$jsonResponse = json_decode($response, true);
$dmsg.= debugmsg("Webservice response", $jsonResponse);

//operation was successful get the token from the response.
if ($jsonResponse['success']==false) {
	$dmsg.= debugmsg('failed:'.$jsonResponse['error']['message']);
	echo 'rule failed!';
} else {
	echo $jsonResponse['result'];
}
?>
```

**Response:** 

```json
{
  "success":true,
  "result":{
     "LISTVIEWBASIC":[
        {
           "tabid":"6",
           "linkid":"43076",
           "linktype":"LISTVIEWBASIC",
           "linklabel":"Send SMS",
           "linkurl":"SMSNotifierCommon.displaySelectWizard(this, \\'Accounts\\');",
           "linkicon":"",
           "sequence":"0",
           "status":false,
           "handler_path":"",
           "handler_class":"",
           "handler":"",
           "onlyonmymodule":"0"
        },
        {
           "tabid":"6",
           "linkid":"244610",
           "linktype":"LISTVIEWBASIC",
           "linklabel":"Generate Document",
           "linkurl":"javascript:showgendoctemplates(\\'Accounts\\');",
           "linkicon":"",
           "sequence":"0",
           "status":false,
           "handler_path":"",
           "handler_class":"",
           "handler":"",
           "onlyonmymodule":"1"
        },
        {
           "tabid":"6",
           "linkid":"43152",
           "linktype":"LISTVIEWBASIC",
           "linklabel":"LBL_SEND_MAIL_BUTTON",
           "linkurl":"return eMail(\\'Accounts\\',this);",
           "linkicon":"",
           "sequence":"0",
           "status":false,
           "handler_path":"",
           "handler_class":"",
           "handler":"",
           "onlyonmymodule":"0"
        },
        {
           "tabid":"6",
           "linkid":"43155",
           "linktype":"LISTVIEWBASIC",
           "linklabel":"LBL_MAILER_EXPORT",
           "linkurl":"return mailer_export();",
           "linkicon":"",
           "sequence":"0",
           "status":false,
           "handler_path":"",
           "handler_class":"",
           "handler":"",
           "onlyonmymodule":"0"
        }
     ]
  }
}
```

#### executeBusinessAction-Operation

The operation that you need to execute a BusinessAction.

**GET URL Format :**
```
http://144.91.100.102:8880/corebos/webservice.php?operation=executeBusinessAction&sessionName={{sessionName}}&businessactionid=43063&context={"ID":"module_rest_idx74"}
```

**Query parameters**
<div class="alpha right"></div>

|Key | Value | Description|
|--- | --- | ---|
|operation | executeBusinessAction | The operation you  need to execute a businessAction|
|sessionName | {{sessionName}} | The value of a hashing value that you need to connect to coreBOS.|
|businessactionid | E.g 43063 | The id of the businessAction that you want to execute|
|context | {"ID":"module_rest_idx74"} | The id of the module and the record id that you want to execute the businessAction.|


!! Only block detail view widgets supported
<br> 

**SessionName** 
<br> 
```
var hash = CryptoJS.MD5(token+accesskey).toString();
```

**Response**
```json
{
    "success": true,
    "result": "<input type=\"hidden\" id=\"comments_parentId\" value=\"74\" /> <table class=\"small\" border=\"0\" cellpadding=\"0\" cellspacing=\"0\" width=\"100%\"> <tr class=\"detailview_block_header comments_block_header\"> <td colspan=\"4\" class=\"dvInnerHeader\"> <div style=\"float: left; font-weight: bold;\"> <div style=\"float: left;\"> <a href=\"javascript:showHideStatus('tblModCommentsDetailViewBlockCommentWidget','aidModCommentsDetailViewBlockCommentWidget','$IMAGE_PATH');\"> <span class=\"exp_coll_block inactivate\"><img id=\"aidModCommentsDetailViewBlockCommentWidget\" src=\"themes//images/activate.gif\" style=\"border: 0px solid rgb(0, 0, 0);\" alt=\"Hide\" title=\"Hide\"></span></a> </span></a> </div><b>&nbsp;Comments Information</b></div> <span style=\"float: right;\"> <img src=\"themes//images/vtbusy.gif\" border=0 id=\"indicatorModCommentsDetailViewBlockCommentWidget\" style=\"display:none;\">\n\t\t\tShow : <select class=\"small\" onchange=\"ModCommentsCommon.reloadContentWithFiltering('DetailViewBlockCommentWidget', '74', this.value, 'tblModCommentsDetailViewBlockCommentWidget', 'indicatorModCommentsDetailViewBlockCommentWidget');\"> <option value=\"All\" selected>All</option> <option value=\"Last5\" >Last 5</option> <option value=\"Mine\" >Mine</option> </select> </span> </td> </tr> </table> <div id=\"tblModCommentsDetailViewBlockCommentWidget\" style=\"display: block;\"> <table class=\"small\" border=\"0\" cellpadding=\"0\" cellspacing=\"0\" width=\"100%\"> <tr style=\"height: 25px;\"> <td colspan=\"4\" align=\"left\" class=\"dvtCellInfo commentCell\"> <div id=\"contentwrap_ModCommentsDetailViewBlockCommentWidget\" style=\"overflow: auto; margin-bottom: 20px; width: 100%; word-break: break-all;\"> <div id=\"comment_id_113830\"> <div id=\"mouseArea_113830\" onmouseover=\"hndMouseOver(19,'113830');\" onmouseout=\"fnhide('crmspanid');\" > <div id=\"dtlview_113830\"> <div class=\"dataField\" id=\"comment_content_113830\" style=\"width: 99%; padding-top: 10px;\">\n\t\t\tçmmnote\n\t\t</div> <div class=\"dataLabel\" style=\"border-bottom: 1px dotted rgb(204, 204, 204); width: 99%; padding-bottom: 5px;color:darkred;\">\n\t\t\tAuthor: Joe Bordes on 2022-02-16 16:47:50\n\t\t</div> </div> <div id=\"editarea_113830\" style=\"display:none\"> <textarea id=\"txtbox_113830\" class=\"detailedViewTextBox\" onFocus=\"this.className='detailedViewTextBoxOn'\" onBlur=\"this.className='detailedViewTextBox'\" cols=\"90\" rows=\"8\">çmmnote</textarea> <br><a href=\"javascript:;\" class=\"detailview_ajaxbutton ajax_save_detailview\" onclick=\"ModCommentsCommon.editComment('113830');\">Save</a> </div> </div> </div> </div> </td> </tr> <tr style=\"height: 25px;\" class='noprint'> <td class=\"dvtCellLabel\" align=\"right\">\n\t\t\tAdd Comment\n\t\t</td> <td width=\"100%\" colspan=\"3\" class=\"dvtCellInfo\" align=\"left\"> <div id=\"editarea_ModCommentsDetailViewBlockCommentWidget\"> <textarea id=\"txtbox_ModCommentsDetailViewBlockCommentWidget\" class=\"detailedViewTextBox\" onFocus=\"this.className='detailedViewTextBoxOn'\" onBlur=\"this.className='detailedViewTextBox'\" cols=\"90\" rows=\"8\"></textarea> <br> <button class=\"slds-button slds-button_success\" title=\"Save\" onclick=\"ModCommentsCommon.addComment('ModCommentsDetailViewBlockCommentWidget', '74');\" style=\"color:#ffffff;\" > <svg class=\"slds-button__icon slds-button__icon_left\" aria-hidden=\"true\"> <use xlink:href=\"include/LD/assets/icons/utility-sprite/svg/symbols.svg#save\"></use> </svg>\n\t\t\t\t\t\tSave\n\t\t\t\t</button> <button class=\"slds-button slds-button_neutral\" title=\"Clear\" onclick=\"document.getElementById('txtbox_ModCommentsDetailViewBlockCommentWidget').value='';\" style=\"margin-left: 0;\" > <svg class=\"slds-button__icon slds-button__icon_left\" aria-hidden=\"true\"> <use xlink:href=\"include/LD/assets/icons/utility-sprite/svg/symbols.svg#redo\"></use> </svg>\n\t\t\t\t\t\tClear\n\t\t\t\t</button> </div> </td> </tr> </table> </div>"
}
```

 


#### executeBusinessAction - coreBOS Webservice Development 

**The operation:**
```json
<?php

//parameters
$params = "sessionName=$cbSessionID";
$params.= "&operation=executeBusinessAction";
$params.= "&businessactionid=43063";
$params.= '&context={"ID":"module_rest_idx74"}';

//Retrieve must be GET Request.
$response = $httpc->fetch_url("$cbURL?$params");
$dmsg.= debugmsg("Raw response (json)", $response);

//decode the json encode response from the server.
$jsonResponse = json_decode($response, true);
$dmsg.= debugmsg("Webservice response", $jsonResponse);

//operation was successful get the token from the response.
if ($jsonResponse['success']==false) {
	$dmsg.= debugmsg('failed:'.$jsonResponse['error']['message']);
	echo 'rule failed!';
} else {
	echo $jsonResponse['result'];
}
?>
```


**Output:**

![output](output.PNG?classes=max)

#### cbQuestionAnswer - Operation

This operation can trigger a [BusinessQuestion](http://corebos.tsolucio.com/documentation/doku.php?id=en:adminmanual:businessquestions#business_questions) and get back the result . The BusinessQuestion can be of several different types such as: Global Search,File,Mermaid,Table,Grid,Number ,Area,RowChart,Scatter,Pie,Map or Funnel.


 **GET URL Format :**

```
http://144.91.100.102:8880/corebos/webservice.php?operation=cbQuestionAnswer&sessionName={{sessionName}}&qid=48x44081
```

**Mermaid BusinessQuestion**
**Query parameters**

<div class="alpha right"></div>

|Key | Value | Description|
|--- | --- | ---|
|operation | cbQuestionAnswer | The operation you  need to execute a businessQuestion|
|sessionName | {{sessionName}} | The value of a hashing value that you need to connect to coreBOS.|
|qid | 48x44081 | The id of the BusinessQuestion that you want to execute|
<br> 

**SessionName**
<br> 
```
var hash = CryptoJS.MD5(token+accesskey).toString();
```
```json
Response
{
    "success": true,
    "result": {
        "columns": "A(( )) -->|contrat| B\nB(( )) -->|Avenants| C(( ))\nC(( )) -->|en cours| H\nD(( )) -->|Terrain| E\nE(( )) -->|Etudes| C(( ))\nF(( )) -->|Plans| G\nG(( )) -->|Métrés| C(( ))\nH((VT)) -->|\"Control<br>Dossier\"| I(( ))\nI(( )) -->|\"Control<br>Prix\"| J\nJ((VA)) --> K\nK((LCS)) --> L\nL((OUV)) --> M\nM((PV)) -->|Solde| N(( ))\nlinkStyle 0 stroke:greenyellow,stroke-width:2px\nlinkStyle 1 stroke:greenyellow,stroke-width:2px\nlinkStyle 2 stroke:greenyellow,stroke-width:2px\nlinkStyle 7 stroke:greenyellow,stroke-width:2px\nlinkStyle 8 stroke:greenyellow,stroke-width:2px\nstyle H fill:greenyellow,stroke:green,stroke-width:4px\nstyle I fill:greenyellow,stroke:green",
        "title": "mermaid",
        "type": "Mermaid",
        "properties": "LR",
        "answer": "graph LR\n\nA(( )) -->|contrat| B\nB(( )) -->|Avenants| C(( ))\nC(( )) -->|en cours| H\nD(( )) -->|Terrain| E\nE(( )) -->|Etudes| C(( ))\nF(( )) -->|Plans| G\nG(( )) -->|Métrés| C(( ))\nH((VT)) -->|\"Control<br>Dossier\"| I(( ))\nI(( )) -->|\"Control<br>Prix\"| J\nJ((VA)) --> K\nK((LCS)) --> L\nL((OUV)) --> M\nM((PV)) -->|Solde| N(( ))\nlinkStyle 0 stroke:greenyellow,stroke-width:2px\nlinkStyle 1 stroke:greenyellow,stroke-width:2px\nlinkStyle 2 stroke:greenyellow,stroke-width:2px\nlinkStyle 7 stroke:greenyellow,stroke-width:2px\nlinkStyle 8 stroke:greenyellow,stroke-width:2px\nstyle H fill:greenyellow,stroke:green,stroke-width:4px\nstyle I fill:greenyellow,stroke:green\n\n"
    }
}
```

#### Pie BusinessQuestion- coreBOS Webservice Development

**Request :**

```json
<?php
//sessionId is obtained from login result.
$params = "sessionName=$cbSessionID&operation=cbQuestionAnswer&qid=44080";
//query must be GET Request.
$response = $httpc->fetch_url("$cbURL?$params");
$dmsg.= debugmsg("Raw response (json) Query",$response);

//decode the json encode response from the server.
$jsonResponse = json_decode($response, true);
$dmsg.= debugmsg("Webservice response Query",$jsonResponse);

if($jsonResponse['success']==false) {
    $dmsg.= debugmsg('query failed: '.$jsonResponse['message']);
	var_dump($jsonResponse['message']);
    echo 'query failed!';
} else {
    $dmsg.= debugmsg('query OK: '.$jsonResponse['result']);
	var_dump($jsonResponse['result']);
    echo 'query OK!';
}
?>
```

**Response :**

```json
array(6) { ["module"]=> string(8) "HelpDesk" ["columns"]=> string(263) "[{"fieldname":"countres","operation":"is","value":"count(ticket_title)","valuetype":"expression","joincondition":"and","groupid":"0"},{"fieldname":"ticketstatus","operation":"is","value":"ticketstatus","valuetype":"fieldname","joincondition":"and","groupid":"0"}]" ["title"]=> string(17) "Ticket per Status" ["type"]=> string(3) "Pie" ["properties"]=> string(51) "{"key_label":"ticketstatus","key_value":"countres"}" ["answer"]=> array(4) { [0]=> array(2) { ["countres"]=> string(1) "5" ["ticketstatus"]=> string(6) "Closed" } [1]=> array(2) { ["countres"]=> string(1) "2" ["ticketstatus"]=> string(11) "In Progress" } [2]=> array(2) { ["countres"]=> string(1) "1" ["ticketstatus"]=> string(4) "Open" } [3]=> array(2) { ["countres"]=> string(1) "1" ["ticketstatus"]=> string(17) "Wait For Response" } } } query OK!
```
#### cbRule - Operation 

This operation allows you to execute a Condition Expression-BusiessMap. This mapping permits us to evaluate an expression in the context of the application and get the result to decide subsequent actions. It accepts two formats, one is a direct expression from the workflow expression engine and the other is a function expression that can be called from inside the system. The function parameters will be changed to the current record values if they exist.

 **GET URL Format :**
 ```
http://144.91.100.102:8880/corebos/webservice.php?operation=cbRule&sessionName={{sessionName}}&conditionid=34033&context=74
```

**Query parameters**
<div class="alpha right"></div>

|Key | Value | Description|
|--- | --- | ---|
|operation | cbRule | The operation you  need to execute a businessMap type Condition Expression or ConditionQuery|
|sessionName | {{sessionName}} | The value of a hashing value that you need to connect to coreBOS.|
|conditionid | 34033 | The id of the BusinessMap that you want to execute|
|context | module_rest_idx74 | The module id and the record_id where you want to execute the BusinessMap|
<br> 

**SessionName**
<br> 
```
var hash = CryptoJS.MD5(token+accesskey).toString();
```

**Condition Expression Map example**

![ce](ce1.PNG?classes=max)

**Response:**
```json
{
    "success": true,
    "result": "Chemex Labs Ltd"
}
```

#### cbRule- coreBOS Webservice Development

**Request :**

```json
<?php
$context = array(
	'record_id' => '74',
);
$context = json_encode($context);
$mapid = '34032';
 
//sessionId is obtained from loginResult.
$params = "sessionName=$cbSessionID";
$params.= "&operation=cbRule";
$params.= "&conditionid=".urlencode($mapid);
$params.= "&context=".urlencode($context);
 
//Retrieve must be GET Request.
$response = $httpc->fetch_url("$cbURL?$params");
$dmsg.= debugmsg("Raw response (json)", $response);
 
//decode the json encode response from the server.
$jsonResponse = json_decode($response, true);
$dmsg.= debugmsg("Webservice response", $jsonResponse);
 
//operation was successful get the token from the response.
if($jsonResponse['success']==false) {
	$dmsg.= debugmsg('failed:'.$jsonResponse['error']['message']);
	echo 'rule failed!';
} else {
	echo $jsonResponse['result'];
}
?>
```

Condition Expression Map example

![ce2](ce2.png?classes=max)

**Response:**
```json
{"success":true,"result":141}
```


































<head>
  <style type="text/css">
    div.alpha + table  { width: 600px; border: 1px solid black }
    div.alpha + table td { border: 1px solid black;border-bottom: 1px solid black; }
    div.alpha + table th { border: 1px solid black;border-bottom: 1px solid black;background-color:#f2f2f2 }
     div.alpha + table tr:nth-child(even) {background: #f2f2f2}

  .max {
  width: 600px ;
 }