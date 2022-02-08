---
title: 'Web service documentation: Operations'
---

Web service documentation: Operations
-------------------------------------

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

      * [[:en:devel:corebosws:login|Login to webservice]]
      * [[:en:devel:corebosws:querylanguage|Query language]]
      * [[:en:devel:corebosws:methodreference|Method Reference]]
      * [[:en:devel:corebosws:convertleadwebservice|Convert Lead Webservice]]
      * [[:en:devel:corebosws:docenhance_examples|Working with Documents]]
      * [[:en:devel:corebosws:getpdfdata|Get inventory modules PDF output]]
      * [[:en:devel:corebosws:getrelatedrecords|get Related Records method]]

------------------------------------------------------------------------

&lt;WRAP right&gt; [Next: Login to
webservice](/en/devel/corebosws/login) | [Table of
Contents](/en/devel/corebosws/tableofcontents) &lt;/WRAP&gt;

------------------------------------------------------------------------
