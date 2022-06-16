---
title: 'Discount on Product and Service Category'
metadata:
    description: 'This business settings module will permit you to define discounts per product/service line and/or clients.'
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
        - extension
    tag:
        - module
---
---
This business settings module will permit you to define discounts per product/service line and/or clients.

===

The goal of this change is to permit direct discounts for each account based on the category of products and/or services. It will permit us, for example, to assign a 10% discount to any account when he buys products in the software category and an 8% discount if he uses services of the technical category. These discounts will be automatically applied when selecting the product/service on the quote, salesorder or invoice.

The modules synchronizes the category picklists on the service and product entities, so, once the change has been applied both picklists will be exactly the same on both modules and can be easily maintained in the picklist editor of either module.

The new Discount Line module also shares this picklist with the two modules. It permits to select the associated account and indicate the amount of discount to apply on any category. The relation of discounts can be seen on the account's +info tab and there is a security check so you can't apply two or more discounts to the same category for the same account.

You can read more about the module in the [coreBOS Price Modification](https://blog.corebos.org/blog/pricecalculation) blog post.

You can download the code from its' [GitHub repository](https://github.com/tsolucio/PriceCalculation)

As usual with our work we can adapt it to your needs. If you don't want the picklists synchronized, want to related to contacts or need any other additional functionality, contact us.