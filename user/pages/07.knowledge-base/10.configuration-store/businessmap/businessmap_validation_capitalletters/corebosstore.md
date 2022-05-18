---
title: Business Mapping:: Validation Brazilian name
metadata:
    description: 'Test with first letter is uppercase, and all words is a valid Brazilian name (with length, number of words and characters)'
    author: 'Ranieri Slemer'
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
        - validation
---

Test with first letter is uppercase, and all words is a valid Brazilian name (with length, number of words and characters)

```php
<map>
<originmodule>
<originname>contacs</originname>
</originmodule>
<fields>
<field>
<fieldname>firstname</fieldname>
<validations>
<validation>
<rule>regex</rule>
<restrictions>
<restriction>''(?=^.{2,60}$)^[A-ZÀÁÂĖÈÉÊÌÍÒÓÔÕÙÚÛÇ][a-zàáâãèéêìíóôõùúç]+(?:[ ](?:das?|dos?|de|e|[A-Z][a-z]+))*$'</restriction>
</restrictions>
</validation>
</validations>
</field>
</fields>
</map>
```

<br>
------------------------------------------------------------------------

[Next](http://localhost/coreBOSDocumentation/knowledge-base/configuration-store/businessmap/businessmapping_salesorder2purchaseorder/id:8da23107042004dfdca1977d0d2d22f7/store:configuration) | Chapter 5: SalesOrder2PurchaseOrder.

------------------------------------------------------------------------