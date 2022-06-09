---
title: '238: Permit sorting of detail view widget blocks'
metadata:
    description: '238: Permit sorting of detail view widget blocks'
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
        - documentation
    tag:
        - issue
---

Issue Reference in Tracker: ~issue:238~

## Detailed Explanation

We have added the rendering process of [Detail View Widget blocks](http://localhost/coreBOSDocumentation/developer-guide/development_framework/develtutorials/add_special_block) into the rendering process of normal blocks. This way we start with the normal blocks (so the first block will ALWAYS be a normal block) and mix in the [special Detail View Widget blocks](http://localhost/coreBOSDocumentation/developer-guide/development_framework/develtutorials/add_special_block) in order.

![](detailviewwidgetsortcontacts.png?width=100%)

We have enhanced the layout editor so you can easily determine where you want these blocks to appear, exactly as you could already do with the normal blocks.

![](detailviewwidgetblocksorting.png?width=100%)