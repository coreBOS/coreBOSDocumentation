---
title: 'Extended Field Information Mapping'
metadata:
    description: 'Define a set of additional features on fields.'
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
        - fieldinfo
---
---
The purpose of this mapping is to define a set of additional features on fields. Instead of adding columns to the vtiger_field table and creating different UI settings options we add this mapping where you can configure the extra information for each field.

===

The accepted format is:

```xml
<map>
  <originmodule>
    <originname>ModuleName</originname>
  </originmodule>
  <fields>
    <field>
      <fieldname>fieldname</fieldname>
      <features>
        <feature>
          <name>feature_name</name>
          <value>feature_value</value>
          <values>
             <value>
               <module>module_name</module>
               <value>value</value>
               ...
             </value>
             ...
           </values>
        </feature>
      </features>
    </field>
  </fields>
</map>
```

A **feature** can have either a unique value or an array of values. If both are given, the unique value will be used.


For example, to define an RTE field we would have:

```xml
<map>
  <originmodule>
    <originname>SalesOrder</originname>
  </originmodule>
  <fields>
    <field>
      <fieldname>description</fieldname>
      <features>
        <feature>
          <name>RTE</name>
          <value>1</value>
        </feature>
      </features>
    </field>
  </fields>
</map>
```

The above map will activate the RTE in the SalesOrder description field.

As with other Business Maps, the name of the record is what will determine if it is used or not and on what module. In this case the name of the record must be: **{MODULENAME}_FieldInfo**. For the example map above to work it must be saved in a record whose name is **SalesOrder_FieldInfo**

The information in this mapping is available directly in the DetailViewUtils and EditViewUtils scripts and also in the Detail and Edit View Smarty templates. You can [study this commit](https://github.com/tsolucio/corebos/commit/97d26c2a7d32a84fee4737e40f099a8166484e64) where we access this information to add generic support for RTE fields.

Another example would be to have different settings for an autocomplete field. Something like this:

```xml
<map>
  <originmodule>
    <originname>Potentials</originname>
  </originmodule>
  <fields>
    <field>
      <fieldname>autocompletefieldx</fieldname>
      <features>
        <feature>
          <name>searchfields</name>
          <value>field1,field2,...,fieldn</value>
        </feature>
        <feature>
          <name>searchcondition</name>
          <value>startswith</value>
        </feature>
        <feature>
          <name>entityfield</name>
          <value>field</value>
        </feature>
        <feature>
          <name>showfields</name>
          <value>field1,field2,...,fieldn</value>
        </feature>
        <feature>
          <name>fillfields</name>
          <value>field1=fillfield1,field2=fillfield2,...,fieldn=fillfieldn</value>
        </feature>
      </features>
    </field>
  </fields>
</map>
```

Which defines that the autocomplete must show the "entityfield" followed by the list of "showfields" to the user while it permits them to search on the list of "searchfields" and then will fill in the "fillfields" with the values of the indicated record fields.

or like this for a multioptional autocomplete field:

```xml
<map>
  <originmodule>
    <originname>Potentials</originname>
  </originmodule>
  <fields>
    <field>
      <fieldname>autocompletefieldx</fieldname>
      <features>
        <feature>
          <name>searchfields</name>
          <values>
            <value>
              <module>Accounts</module>
              <value>field1,field2,...,fieldn</value>
            </value>
            <value>
              <module>Contacts</module>
              <value>field1,field2,...,fieldn</value>
            </value>
          </values>
        </feature>
        <feature>
          <name>searchcondition</name>
          <value>startswith</value>
        </feature>
        <feature>
          <name>entityfield</name>
          <values>
            <value>
              <module>Accounts</module>
              <value>field</value>
            </value>
            <value>
              <module>Contacts</module>
              <value>field</value>
            </value>
          </values>
        </feature>
        <feature>
          <name>showfields</name>
          <values>
            <value>
              <module>Accounts</module>
              <value>field1,field2,...,fieldn</value>
            </value>
            <value>
              <module>Contacts</module>
              <value>field1,field2,...,fieldn</value>
            </value>
          </values>
        </feature>
        <feature>
          <name>fillfields</name>
          <values>
            <value>
              <module>Accounts</module>
              <value>field1=fillfield1,field2=fillfield2,...,fieldn=fillfieldn</value>
            </value>
            <value>
              <module>Contacts</module>
              <value>field1=fillfield1,field2=fillfield2,...,fieldn=fillfieldn</value>
            </value>
          </values>
        </feature>
      </features>
    </field>
  </fields>
</map>
```

## Configuring Autocomplete and MultiSelect Autocomplete Fields

[Continue reading here for more information on how to configure an autocomplete functionality on a field in coreBOS](autocomplete)

## Configuring Combobox with static values Fields

[Continue reading here for more information on how to configure a combobox functionality on a field in coreBOS](combobox)

## Configuring Multipicklists

```xml
<map>
  <originmodule>
    <originname>Accounts</originname>
  </originmodule>
  <fields>
    <field>
      <fieldname>cf_732</fieldname>
      <features>
        <feature>
          <name>columns</name>
          <value>10</value>
        </feature>
        <feature>
          <name>width</name>
          <value>350</value>
        </feature>
      </features>
    </field>
  </fields>
</map>
```

## Configuring Textarea Height

```xml
<map>
  <originmodule>
    <originname>Accounts</originname>
  </originmodule>
  <fields>
    <field>
      <fieldname>description</fieldname>
      <features>
        <feature>
          <name>height</name>
          <value>150</value>
        </feature>
      </features>
    </field>
  </fields>
</map>
```


<br>
------------------------------------------------------------------------

[Next](http://localhost/coreBOSDocumentation/configuration-tools/business-maps/record_access_control) | Chapter 5: Record Access Control.

------------------------------------------------------------------------