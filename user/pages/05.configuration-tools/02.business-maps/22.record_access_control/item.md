---
title: 'Record Access Control'
metadata:
    description: 'Record Access Control.'
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
        - adminmanuals
        - businessmappings
    tag:
        - recordaccesscontrol
---
---

<div class="notices blue">
For more advanced customizations of
the permission system and how that compares to Record Access Control
look at the [coreBOS Permission
Hooks](http://corebos.org/documentation/doku.php?id=en:devel:corebos_permission_hooks).
</div>

The accepted format is:
```xml
    <map>
      <originmodule>
        <originid>22</originid>  {optional}
        <originname>SalesOrder</originname>
      </originmodule>
      <listview>
      <c>1</c>  Add button
      <r>1</r>  View record
      <u>1</u>  Edit action
      <d>1</d>  Delete action
      {conditiongroup}  Optional
      </listview>
      <detailview>
      <c>1</c>  Duplicate button
      <r>1</r>  View record
      <u>1</u>  Edit action
      <d>1</d>  Delete action
      {conditiongroup}  Optional
      </detailview>
      <relatedlists>
        <relatedlist>
          <modulename>Invoice</modulename>
          <c>1</c>  Add button
          <r>1</r>  View list
          <u>1</u>  Edit action
          <d>1</d>  Delete action
          <s>1</s>  Select button
          {conditiongroup}  Optional
        </relatedlist>
        .....
      </relatedlists>
      </map>
```
where *{condtiongroup}* is
```xml
    <condition>
       <businessrule>{cbMapID}</businessrule>
       <c>1</c>  Add button
       <r>1</r>  View list
       <u>1</u>  Edit action
       <d>1</d>  Delete action
       <s>1</s>  Select button
    </condition>
```
and the business rule must be of type **ConditionQuery** or
**ConditionExpression** and return a number bigger than zero, a boolean
true, the string 'true' or the string 'yes' to be accepted. Any other
value will be false.

If the condition is a **ConditionQuery**, the SQL will be executed with
only one parameter, which is the CRMID of the Record launching the
Record Access Control, if it is a **ConditionExpression** it will be
executed with the full set of fields of the Record launching the Record
Access Control. The *CRUDS* settings contained inside the
&lt;condition&gt; will override the default settings if the condition is
true.

This Business Mapping is tied with the workflow system. Through the
workflow system you can assign conditions for the mapping to be applied.
For example, we can easily block editing and deleting of a project task
depending on the status of it's parent project. That would look like
this. First a workflow and business mapping to block the projects that
are closed:

![](racbm_01.png?width=100%)

Next a workflow and mapping to block the project tasks:

![](racbm_02.png?width=100%)

You could easily add another condition to the workflows so that they
applied only for certain users (for example).

Condition Query Example
-----------------------

As an example of the use of a condition query, we could add a rule
whereas we permit adding ProjectTask to a Closed Project if the related
Account has at least one potential record associated:
```xml
     <relatedlists>
        <relatedlist>
          <modulename>ProjectTask</modulename>
          <c>0</c>
          <r>1</r> 
          <u>1</u>
          <d>0</d>
          <s>0</s>
    <condition>
    <businessrule>27183</businessrule>
          <c>1</c>
          <r>0</r> 
          <u>0</u>
          <d>1</d>
          <s>1</s>
    </condition>
        </relatedlist>
        <relatedlist>
          <modulename>ProjectMilestone</modulename>
          <c>0</c>
          <r>1</r> 
          <u>0</u>
          <d>0</d>
          <s>0</s>
        </relatedlist>
      </relatedlists>
```
where the business rule with crmid=27183 is of type conditionquery and
contains:
```xml
    <map>
    <sql>SELECT count(*) as numpots
    FROM vtiger_potential
    INNER JOIN vtiger_account on vtiger_potential.related_to = vtiger_account.accountid
    INNER JOIN vtiger_project on vtiger_project.linktoaccountscontacts = vtiger_account.accountid
    INNER JOIN vtiger_crmentity ce ON ce.crmid=vtiger_potential.potentialid
    WHERE ce.deleted=0 AND vtiger_project.projectid =?
    </sql>
    <return>numpots</return>
    </map>
```
Block Sent Emails Delete and Edit Example
-----------------------------------------

Another example is to block editing and deleting of sent emails on the
list view, which would be something like this:

![](racsentemails.png?width=100%)

with this mapping:
```xml
    <map>
      <originmodule>
        <originname>Emails</originname>
      </originmodule>
        <listview>
      <u>0</u>
      <d>0</d>
        </listview>
      </map>
```
Block Tickets if assigned user is not creator
---------------------------------------------

<iframe width="578" height="321" src="https://www.youtube.com/embed/Iryw1xw78t4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Accessing via web service
-------------------------

RAC rules must be evaluated on a per Module-Action-Record basis. For
each combination of these three values, a search must be made in the
workflow system, then each candidate RAC workflow must have its'
conditions evaluated, and then, once one is found the map must be read
and processed according to the triple given.

coreBOS does exactly this process among some other steps in the function
**isPermitted** It is this function that we need to call to get the RAC
rules in our external applications. This can be easily achieved using a
condition expression business map of type function set to isPermitted
like this:
```xml
    <map>
    <function>
        <name>isPermitted</name>
        <parameters>
            <parameter>permitted_module</parameter>
            <parameter>permitted_action</parameter>
            <parameter>permitted_record</parameter>
        </parameters>
    </function>
    </map>
```
which can be called like this:
```js
    $response = $cbconn->doInvoke(
        'cbRule',
        array(
            'conditionid' => '37x118348',
            'context' => json_encode(
                array(
                    'record_id' => '37x118348',
                    'permitted_module' => 'cbMap',
                    'permitted_action' => 'ListView',
                    'permitted_record' => '',
                )
            ),
        ),
        'GET'
    );
    var_dump($response);
```
You can also call this with the map name. Let's suppose that the map
above has the name **RACRulePermittedCheck** you could do this:
```js
    $response = $cbconn->doInvoke(
        'cbRule',
        array(
            'conditionid' => 'RACRulePermittedCheck',
            'context' => json_encode(
                array(
                    'record_id' => '11x74',
                    'permitted_module' => 'Accounts',
                    'permitted_action' => 'EditView',
                    'permitted_record' => '11x74',
                )
            ),
        ),
        'GET'
    );
    var_dump($response);
```
In general, the idea is:
```js
    {
     "conditionid": "RACRulePermittedCheck",
     "context": {
       "record_id": record you want to know the permissions for may be empty (I think),
       "permitted_module": module name of the record you want the permission for
       "permitted_action": the action you want to know the access fo
       "permitted_record": in case the action requires an ID of a record put it here
     }
    }
```

<br>
------------------------------------------------------------------------

[Next](../17.list_columns) | Chapter 6: List Columns.

------------------------------------------------------------------------