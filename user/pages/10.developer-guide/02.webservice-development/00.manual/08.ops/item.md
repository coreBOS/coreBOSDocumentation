---
title: 'Web service documentation: Operations'
metadata:
    description: 'coreBOS has a rich set of generic operations that can be used on any module in the application'
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
        - development
        - webservice
    tag:
        - operations
---

---
coreBOS has a rich set of generic operations that can be used on any
module in the application.

The next chapters will cover all of these operations from a functional
or reference point of view depending on the importance of each
operation.

Before we start we will layout some conventions used in subsequent parts
of the manual:

**Id Format**: `objectTypeId 'x' objectId` the first number represents
the module identifier while the second number represents the internal
identifier of the record. They are separated by a lower case x, like
this: 3x40

**Object**: a JSON object which represents a field-value mapping of a
record in the application. Each module has its own set of fields so each
object will have a different set of fields to match the module it
represents. Each object has a common set of fields which are:

-   **id**: the record identifier as explained above
-   **cbuuid**: this is a universal unique identifier of the record
    which can be used in any web service operation in place of the ID.
    This permits us to easily share information between different
    coreBOS installs.

**Map**: an associative array of key-value entries, usually represented
by a simple JSON object. the only difference with an **Object** is that
it does not contain the identifier fields. This is typically used in
create operations.

**Timestamp**: a long integer representing a [UNIX
Epoch](http://es.wikipedia.org/wiki/Timestamp)

Let's dive into the operations.

-   <a href="http://localhost/coreBOSDocumentation/configuration-tools/webservice-development/login">Login to webservice</a>
-   <a href="http://localhost/coreBOSDocumentation/configuration-tools/webservice-development/querylanguage">Query language</a>
-   <a href="http://localhost/coreBOSDocumentation/configuration-tools/webservice-development/methodreference">Method Reference</a>
-   <a href="http://localhost/coreBOSDocumentation/configuration-tools/webservice-development/convertleadwebservice">Convert Lead Webservice</a>
-   <a href="http://localhost/coreBOSDocumentation/configuration-tools/webservice-development/docenhance">Working with Documents</a>
-   <a href="http://localhost/coreBOSDocumentation/configuration-tools/webservice-development/getpdfdata">Get inventory modules PDF output</a>
-   <a href="http://localhost/coreBOSDocumentation/configuration-tools/webservice-development/getrelatedcontrols">get Related Records method</a>


<br>
------------------------------------------------------------------------

[Next](http://localhost/coreBOSDocumentation/configuration-tools/webservice-development/login)| Chapter 3: Login to webservice.

------------------------------------------------------------------------