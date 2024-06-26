---
title: 'Integración vtigerCRM y wordpress e-commerce plugin'
metadata:
    description: 'Integración vtigerCRM y wordpress e-commerce plugin'
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
        - integration
    tag:
        - oocommerce
---

We have added support to vtiger CRM webservice interface to support quotes/SO/PO/invoice. So this alone is a very interesting extension to vtiger CRM making integrations a lot easier.

===

We have created a patch based on wordpress with the [WordPress eCommerce MarketPress](http://wordpress.org/extend/plugins/wordpress-ecommerce) eCommerce plugin so that when a purchase is made in wordpress we create a new sales order in vtiger CRM

This extension requires modifying vtiger CRM code to add product line support in the REST interface and then modifying the wordpress code to hook into the purchase process and send the information to vtiger CRM. The change looks for the account in vtiger CRM based on email and if it is found will create the SO attached to this account, if not found a new account will be created with the information available from wordpress.

For the products we use wordpress SKU to look for a vtiger CRM product with that product code, if found we use that product and if not we create a new product.

Since all this is happening through vtiger CRM REST webservice any workflows that may be defined inside vtiger CRM will be launched.

We are now in position to enhance this functionality inside wordpress or any other eCommerce site.

Contact us for furhter information

Example:

![](shoppingcart.png?width=100%)

![](list_quote_sin.png?width=100%)

![](confirm_purchase.png?width=100%)

![](list_quote.png?width=100%)

![](new_quote.png?width=100%)

![](new_account.png?width=100%)

------------------------------------------------------------------------

[Next](../05.corebosmail) | Chapter 5: Roundcube coreBOS CRM Integration

------------------------------------------------------------------------