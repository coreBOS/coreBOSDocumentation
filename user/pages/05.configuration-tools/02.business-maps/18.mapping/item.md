---
title: '(Field) Mapping Business Mapping'
metadata:
    description: 'filling in fields of a new record when coming from another module record or setting default values for the module you are creating.'
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
        - businessmappings
    tag:
        - mapping
        - field
---

This business rule serves the purpose of filling in fields of a new record when coming from another module's record or setting default values for the module you are creating. For example, when creating an Invoice from a SalesOrder or an Opportunity from a Contact.

===

It will permit you to define what values you want to copy from the origin module or simply what values you want to set by default when creating in the way.

 !!! When creating a new record you always have access to all the fields of the current user using the FIELD or TEMPLATE types. For example: `$(assigned_user_id : (Users) first_name)`

The accepted format is:

```xml
<map>
  <originmodule>
    <originname>SalesOrder</originname>
  </originmodule>
  <targetmodule>
    <targetname>Invoice</targetname>
  </targetmodule>
  <fields>
    <field>
      <fieldname>subject</fieldname>   {destination field on invoice}
      <Orgfields>  {if more than one is present they will be concatenated with the delimiter}
        <Orgfield>
          <OrgfieldName>subject</OrgfieldName>
          <OrgfieldID>FIELD</OrgfieldID>
        </Orgfield>
        <Orgfield>
          <OrgfieldName>sostatus</OrgfieldName>
          <OrgfieldID>FIELD</OrgfieldID>
        </Orgfield>
        <Orgfield>
          <OrgfieldName>_FromSO</OrgfieldName>  {this is a constant string}
          <OrgfieldID>CONST</OrgfieldID>
        </Orgfield>
        <delimiter>;</delimiter>
      </Orgfields>
      <master>true|false</master> {optional: used for integration mapping between two systems}
    </field>
      <field>
      <fieldname>description</fieldname>   {destination field on invoice}
      <Orgfields>  {if more than one is present they will be concatenated with the delimiter}
        <Orgfield>
          <OrgfieldName>$(assigned_user_id : (Users) first_name)</OrgfieldName>
          <OrgfieldID>FIELD</OrgfieldID>
        </Orgfield>
        <Orgfield>
          <OrgfieldName>$(assigned_user_id : (Users) last_name)</OrgfieldName>
          <OrgfieldID>FIELD</OrgfieldID>
        </Orgfield>
        <Orgfield>
          <OrgfieldName>The user assigned to the Sales Order is: $(assigned_user_id : (Users) first_name) $(assigned_user_id : (Users) last_name)</OrgfieldName>
          <OrgfieldID>TEMPLATE</OrgfieldID>
        </Orgfield>
        <Orgfield>
          <OrgfieldName>account_id</OrgfieldName>
          <OrgfieldID>RULE</OrgfieldID>
          <Rule>business rule name or ID</Rule>
        </Orgfield>
        <delimiter> - </delimiter>
      </Orgfields>
    </field>
    <field>
      <fieldname>due_date</fieldname>   {destination field on invoice}
      <Orgfields>
        <Orgfield>
          <OrgfieldName>add_days(get_date('today'), 30)</OrgfieldName>
          <OrgfieldID>EXPRESSION</OrgfieldID>
          <postProcess>intval</postProcess>
        </Orgfield>
      </Orgfields>
    </field>
    <field>
      .....
    </field>
  </fields>
</map>
```

The `OrgfieldID` directive may have 5 values:

* FIELD: the OrgfieldName contains a field or field expression
* CONST: the OrgfieldName will be used "as is", no transformation applied
* TEMPLATE: the OrgfieldName will be used as a string template parsed by the Message engine (like an email)
* EXPRESSION: the OrgfieldName contains a workflow expression and will be parsed by the workflow engine using the context of the record
* RULE: the OrgfieldName will contain the ID or name of a business rule. See below for more information.

Each `OrgfieldID` directive may have a `postProcess` directive. This permits us to do some additional processing in cases where the `OrgfieldID` directive is not expressive enough. Usually this is used to specify the format of the result to be used in the mapping. For example, in general coreBOS uses strings for all its' results but we may need to use an integer or float or strip slashes that are returned from the expression before inserting it into the resulting array. Some of the methods that can be used are:

- intval - Get the integer value of a variable
- boolval - Get the boolean value of a variable
- floatval - Get float value of a variable
- addslashes Quote string with slashes
- stripslashes - Un-quotes a quoted string
- htmlspecialchars - Convert special characters to HTML entities
- quotemeta - Quote meta characters
- json_encode
- json_decode

For this map to be applied, the name of the mapping must follow a specific format which is

```
{OriginModule}2{TargetModule}
```
you must create the mapping exactly with that name and the module names must be exactly their internal module name. If you want to have more than one mapping that will be applied depending on the user you must also create a new entry in the Global Variable name picklist called

```
BusinessMapping_{OriginModule}2{TargetModule}
```

and then define a Global Variable of this type and select the corresponding Business Mapping.

For example, if you create a Mapping called *Contacts2Potentials* and set it's mapping to the one below, you will get the name set to the contact's name, the closing date set to 30 days from now and the sales stage set to Qualifying.

Then call the create page of Potentials from a link passing in the variable **cbfromid** or from a related list, which already has this variable.

```xml
<map>
  <originmodule>
    <originname>Contacts</originname>
  </originmodule>
  <targetmodule>
    <targetname>Potentials</targetname>
  </targetmodule>
  <fields>
    <field>
      <fieldname>potentialname</fieldname>
      <Orgfields>
        <Orgfield>
          <OrgfieldName>firstname</OrgfieldName>
        </Orgfield>
        <Orgfield>
          <OrgfieldName>lastname</OrgfieldName>
        </Orgfield>
        <delimiter> </delimiter>
      </Orgfields>
    </field>
    <field>
      <fieldname>closingdate</fieldname>
      <Orgfields>
        <Orgfield>
          <OrgfieldName>add_days(get_date('today'), 30)</OrgfieldName>
          <OrgfieldID>expression</OrgfieldID>
        </Orgfield>
      </Orgfields>
    </field>
    <field>
        <fieldname>sales_stage</fieldname>
        <Orgfields>
            <Orgfield>
                <OrgfieldName>Qualification</OrgfieldName>
                <OrgfieldID>CONST</OrgfieldID>
            </Orgfield>
        </Orgfields>
    </field>
  </fields>
</map>
```

Another example for User default values:

```xml
<map>
  <originmodule>
    <originname>Users</originname>
  </originmodule>
  <targetmodule>
    <targetname>Users</targetname>
  </targetmodule>
  <fields>
    <field>
      <fieldname>currency_grouping_pattern</fieldname>
      <Orgfields>
        <Orgfield>
          <OrgfieldName>123456789</OrgfieldName>
          <OrgfieldID>CONST</OrgfieldID>
        </Orgfield>
      </Orgfields>
    </field>
    <field>
      <fieldname>currency_decimal_separator</fieldname>
      <Orgfields>
        <Orgfield>
          <OrgfieldName>.</OrgfieldName>
          <OrgfieldID>CONST</OrgfieldID>
        </Orgfield>
      </Orgfields>
    </field>
    <field>
      <fieldname>QLTQ</fieldname>
      <Orgfields>
        <Orgfield>
          <OrgfieldName>QLTQ</OrgfieldName>
          <OrgfieldID>CONST</OrgfieldID>
        </Orgfield>
      </Orgfields>
    </field>
    <field>
      <fieldname>ALVT</fieldname>
      <Orgfields>
        <Orgfield>
          <OrgfieldName>ALVT</OrgfieldName>
          <OrgfieldID>CONST</OrgfieldID>
        </Orgfield>
      </Orgfields>
    </field>
    <field>
      <fieldname>tagcloudview</fieldname>
      <Orgfields>
        <Orgfield>
          <OrgfieldName>false</OrgfieldName>
          <OrgfieldID>CONST</OrgfieldID>
        </Orgfield>
      </Orgfields>
    </field>
    <field>
      <fieldname>showtagas</fieldname>
      <Orgfields>
        <Orgfield>
          <OrgfieldName>vring</OrgfieldName>
          <OrgfieldID>CONST</OrgfieldID>
        </Orgfield>
      </Orgfields>
    </field>
  </fields>
</map>
```

You can [see an example of converting a Contact into an Account in the Business Mapping Store](/en/adminmanual/businessmappings/store/contact2accounts).

And there is an explanation and [small example of Invoice default values here.](http://discussions.corebos.org/thread-338-post-1723.html#pid1723)

Another [example with Help Desk default values in the forum.](http://discussions.corebos.org/thread-346-post-1772.html#pid1772)

## Rule Directive

The rule directive will permit us to launch a [coreBOS Business Rule](/en/devel/corebos_rules) and save the result in the field. This opens the possibilities to launch a query, a workflow expression or a decision table.

You can accomplish the expression and template features with the Rule as it can do that and more.

For example, we may be given a code that we have to search in another module to save a value that comes from there. In this case, we need to launch a query so we would set up a Business Map (Rule) of type [Condition Query](../04.condition-query/) with something like this:

```sql
SELECT contactid
FROM vtiger_contactdetails
JOIN vtiger_contactscf on vtiger_contactdetails.contactid=vtiger_contactscf.contactid
where cf_1518=?
```

Let's suppose we called this business map "getContactFromSeller", then we would add the directive:

```xml
<Orgfield>
  <OrgfieldName>contact_id</OrgfieldName>
  <OrgfieldID>RULE</OrgfieldID>
  <Rule>getContactFromSeller</Rule>
</Orgfield>
```

## Accessing via web service

This type of map can be processed using the **ProcessMap** end-point
