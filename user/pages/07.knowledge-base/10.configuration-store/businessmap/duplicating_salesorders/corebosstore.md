---
title: 'Duplicating Sales Orders'
metadata:
    description: 'Business Map to Duplicate Sales Orders'
    author: 'MajorLabel'
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
        - businessmappings
        - configuration
    tag:
        - fieldmapping
---

```xml
<map>
<originmodule>
  <originname>SalesOrder</originname>
</originmodule>
<targetmodule>
  <targetname>SalesOrder</targetname>
</targetmodule>
<fields>
  <field>
    <fieldname>sostatus</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>Created</OrgfieldName> { Set the status to "Created" regardless of the source SO }
        <OrgfieldID>CONST</OrgfieldID>
      </Orgfield>
     </Orgfields>
  </field>
  <field>
    <fieldname>ship_street</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>$(account_id : (Accounts) ship_street)</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
     </Orgfields>
  </field>
  <field>
    <fieldname>bill_street</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>$(account_id : (Accounts) bill_street)</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
     </Orgfields>
  </field>
  <field>
    <fieldname>bill_city</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>$(account_id : (Accounts) bill_city)</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
     </Orgfields>
  </field>
  <field>
    <fieldname>ship_city</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>$(account_id : (Accounts) ship_city)</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
     </Orgfields>
  </field>
  <field>
    <fieldname>bill_code</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>$(account_id : (Accounts) bill_code)</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
     </Orgfields>
  </field>
  <field>
    <fieldname>ship_code</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>$(account_id : (Accounts) ship_code)</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
     </Orgfields>
  </field>
  <field>
    <fieldname>ship_country</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>$(account_id : (Accounts) ship_country)</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
     </Orgfields>
  </field>
  <field>
    <fieldname>bill_country</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>$(account_id : (Accounts) bill_country)</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
     </Orgfields>
  </field>
</fields>
</map>
```

<br>
------------------------------------------------------------------------

[Next](http://localhost/coreBOSDocumentation/knowledge-base/configuration-store/businessmap/contacts2accounts/id:37247bed69140cef25a6eeb241753653/store:configuration) | Chapter 2: Contacts2Accounts.

------------------------------------------------------------------------