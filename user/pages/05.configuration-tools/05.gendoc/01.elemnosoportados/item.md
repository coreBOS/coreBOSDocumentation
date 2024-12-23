---
title: 'Documentation Generation::Non Supported Elements'
metadata:
    description: 'TNon Supported Elements'
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
        - gendoc

---
## Non Supported Elements

-   Form Elements (checkbox and similar). We will not implement these, too much work for what they are worth.
-   Headers: Some headers are (incorrectly?) saved as paragraphs in the .xml. These do not work. The OpenDocument manual says: "If you use non-numbered Heading style from the stylist, OpenOffice.org will insert a < text:p >, not a < text:h > element." I have no idea how it knows it is a header.
-   Some Calculated Fields
-   bullet points (maybe some others) inside table cells. This is an error and will be corrected at some point in the future
-   "foreach" on the same module will not work. This will be implemented/corrected at some point in the future.


## Documentation Generation::Discarded Elements
```php
<office:text text:use-soft-page-breaks="true">  <text:soft-page-break />
```
We eliminate these during the conversion because they aren't significant where they are. These elements mark the end of a movable page, since we are adding and deleting text most of them are going to move anyway and OpenOffice will reestablish them when the document is opened and we will have to fix them manually, so it is better not to have them.

[Next](../02.gendocejemplos)| Chapter 4: GenDoc::Examples

------------------------------------------------------------------------