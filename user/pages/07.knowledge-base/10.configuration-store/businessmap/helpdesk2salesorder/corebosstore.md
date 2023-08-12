---
title: Business Mapping:: HelpDesk2SalesOrder
metadata:
    description: 'If you create a direct (1:M) relation between HelpDesk and SalesOrder, this mapping created will fill in some fields on the SalesOrder'
    author: 'Luke majorlabel.nl'
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
    tag:
        - fieldmapping
---

If you create a direct (1:M) relation between HelpDesk and SalesOrder, [this mapping created by Luke](http://discussions.corebos.org/thread-633.html) will fill in some fields on the SalesOrder

===

```php
<map>
  <originmodule>
    <originid>13</originid>
    <originname>HelpDesk</originname>
  </originmodule>
  <targetmodule>
    <targetid>22</targetid>
    <targetname>SalesOrder</targetname>
  </targetmodule>
  <fields>
    <field>
      <fieldname>subject</fieldname>
      <fieldID>370</fieldID>
      <Orgfields>
        <Orgfield>
          <OrgfieldName>From ticket:</OrgfieldName>
          <OrgfieldID>CONST</OrgfieldID>
        </Orgfield>
        <Orgfield>
          <OrgfieldName>ticket_title</OrgfieldName>
          <OrgfieldID>159</OrgfieldID>
        </Orgfield>
        <Orgfield>
          <OrgfieldName>ticket_no</OrgfieldName>
          <OrgfieldID>146</OrgfieldID>
        </Orgfield>
<delimiter> </delimiter>
      </Orgfields>
    </field>
    <field>
      <fieldname>account_id</fieldname>
      <fieldID>389</fieldID>
      <Orgfields>
        <Orgfield>
          <OrgfieldName>parent_id</OrgfieldName>
          <OrgfieldID>148</OrgfieldID>
        </Orgfield>
      </Orgfields>
    </field>
    <field>
      <fieldname>cf_939</fieldname>
      <Orgfields>
        <Orgfield>
          <OrgfieldName>description</OrgfieldName>
          <OrgfieldID>FIELD</OrgfieldID>
        </Orgfield>
      </Orgfields>
    </field>
  <field>
    <fieldname>ship_street</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>$(parent_id : (Accounts) ship_street)</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
     </Orgfields>
  </field>
  <field>
    <fieldname>bill_street</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>$(parent_id : (Accounts) bill_street)</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
     </Orgfields>
  </field>
  <field>
    <fieldname>bill_city</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>$(parent_id : (Accounts) bill_city)</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
     </Orgfields>
  </field>
  <field>
    <fieldname>ship_city</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>$(parent_id : (Accounts) ship_city)</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
     </Orgfields>
  </field>
  <field>
    <fieldname>bill_code</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>$(parent_id : (Accounts) bill_code)</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
     </Orgfields>
  </field>
  <field>
    <fieldname>ship_code</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>$(parent_id : (Accounts) ship_code)</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
     </Orgfields>
  </field>
  <field>
    <fieldname>ship_country</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>$(parent_id : (Accounts) ship_country)</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
     </Orgfields>
  </field>
  <field>
    <fieldname>bill_country</fieldname>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>$(parent_id : (Accounts) bill_country)</OrgfieldName>
        <OrgfieldID>FIELD</OrgfieldID>
      </Orgfield>
     </Orgfields>
  </field>
  </fields>
</map>
```

<br>
------------------------------------------------------------------------

[Next](../businessmap_validation_capitalletters) | Chapter 4: Validation Brazilian name.

------------------------------------------------------------------------