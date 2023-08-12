---
title: invoice2cobropagoamountdue
metadata:
    description: 'Copy Amount Due field instead of Total Amount when adding Payments to Invoice in coreBOSCRM'
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

In coreBOSCRM, there is a financial block to control the status of partial payments and pending amounts. This Field Mapping will copy the pending Amount Due field instead of Total Amount when adding Payments to an Invoice.

===

```php
<map>
  <originmodule>
    <originname>Invoice</originname>
  </originmodule>
  <targetmodule>
    <targetname>CobroPago</targetname>
  </targetmodule>
  <fields>
    <field>
      <fieldname>amount</fieldname>
      <Orgfields>
        <Orgfield>
          <OrgfieldName>amount_due</OrgfieldName>
          <OrgfieldID>778</OrgfieldID>
        </Orgfield>
      </Orgfields>
    </field>
  </fields>
</map>
```
<div class="notices red">
You will have to manually add the <strong>"cbfromid"</strong> parameter to the "Add Payment" action.
</div>


<br>
------------------------------------------------------------------------

[Next](../vendoraddresspo) | Chapter 7: PurchaseOrder_FieldDependency.

------------------------------------------------------------------------