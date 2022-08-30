---
title: businessmapping_salesorder2purchaseorder
metadata:
    description: 'Convert a SalesOrder into a PurchaseOrder'
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
    tag:
        - fieldmapping
---
```php
<map>
<originmodule>
  <originid>22</originid>
  <originname>SalesOrder</originname>
</originmodule>
<targetmodule>
  <targetid>21</targetid>
  <targetname>PurchaseOrder</targetname>
</targetmodule>
<fields>
  <field>
    <fieldname>ship_street</fieldname>
    <fieldID>356</fieldID>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>ship_street</OrgfieldName>
        <OrgfieldID>396</OrgfieldID>
      </Orgfield>
     </Orgfields>
  </field>
  <field>
    <fieldname>ship_city</fieldname>
    <fieldID>358</fieldID>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>ship_city</OrgfieldName>
        <OrgfieldID>398</OrgfieldID>
      </Orgfield>
     </Orgfields>
  </field>
  <field>
    <fieldname>ship_code</fieldname>
    <fieldID>362</fieldID>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>ship_code</OrgfieldName>
        <OrgfieldID>402</OrgfieldID>
      </Orgfield>
     </Orgfields>
  </field>
  <field>
    <fieldname>ship_country</fieldname>
    <fieldID>364</fieldID>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>ship_country</OrgfieldName>
        <OrgfieldID>404</OrgfieldID>
      </Orgfield>
     </Orgfields>
  </field>
  <field>
    <fieldname>bill_street</fieldname>
    <fieldID>355</fieldID>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>{YOUR ADDRESS}</OrgfieldName>
        <OrgfieldID>CONST</OrgfieldID>
      </Orgfield>
     </Orgfields>
  </field>
  <field>
    <fieldname>bill_city</fieldname>
    <fieldID>357</fieldID>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>{YOUR TOWN}</OrgfieldName>
        <OrgfieldID>CONST</OrgfieldID>
      </Orgfield>
     </Orgfields>
  </field>
  <field>
    <fieldname>bill_code</fieldname>
    <fieldID>361</fieldID>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>{YOUR ZIPCODE}</OrgfieldName>
        <OrgfieldID>CONST</OrgfieldID>
      </Orgfield>
     </Orgfields>
  </field>
  <field>
    <fieldname>bill_country</fieldname>
    <fieldID>363</fieldID>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>{YOUR COUNTRY}</OrgfieldName>
        <OrgfieldID>CONST</OrgfieldID>
      </Orgfield>
     </Orgfields>
  </field>
  <field>
    <fieldname>subject</fieldname> <!-- Optional: autofill subject -->
    <fieldID>333</fieldID>
    <Orgfields>
      <Orgfield>
        <OrgfieldName>Salesorder:</OrgfieldName>
        <OrgfieldID>CONST</OrgfieldID>
      </Orgfield>
      <Orgfield>
        <OrgfieldName>subject</OrgfieldName>
        <OrgfieldID>370</OrgfieldID>
      </Orgfield>
      <delimiter> </delimiter>
     </Orgfields>
  </field>
</fields>
</map>
```


<br>
------------------------------------------------------------------------

[Next](../invoice2cobropagoamountdue) | Chapter 6: Invoice2CobroPago Amount Due.

------------------------------------------------------------------------