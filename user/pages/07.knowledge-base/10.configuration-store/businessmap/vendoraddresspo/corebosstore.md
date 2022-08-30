---
title: vendoraddresspo
metadata:
    description: 'This map fills in the Purchase Order Billing address when a vendor is selected'
    author: 'JPL TSolucio, S.L.'
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
```php
<map>
  <originmodule>
    <originname>PurchaseOrder</originname>
  </originmodule>
<dependencies>
<dependency>
    <field>vendor_id</field>
    <actions>
        <function>
            <field>vendor_id</field>
            <name>fieldDep_GetField</name>
            <parameters>
              <parameter>street,city,state,code,country,postalcode</parameter>
              <parameter>bill_street,bill_city,bill_state,bill_code,bill_country,bill_pobox</parameter>
            </parameters>
        </function>
    </actions>
</dependency>
</dependencies>
</map>
```


<br>
------------------------------------------------------------------------

[Next](../../changeset/01.convertcountry2picklist) | Chapter 8: Convert Country field to picklist.

------------------------------------------------------------------------