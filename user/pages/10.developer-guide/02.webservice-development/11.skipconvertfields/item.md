---
title: 'How to specify the format of your fields when sending in through web service'
metadata:
    description: 'How to specify the format of your fields when sending in through web service'
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
        - howto
---

In the default behaviour, a web service call to either **revise** or **update** will demand you to make sure all fields are sent to coreBOS in the format of your current user. This applies in particular to number and currency fields, but also to date fields.

===

Let’s say you use user ‘John’ to login to coreBOS through a web service
in a remote application (maybe some customer portal). John has his
preferences stored in the user settings page for his user. He likes his
thousands separator to be a dot, his decimals separator to be a comma
and he wants only two decimals. So his currency fields and numbers would
be formatted like:

1.234,56

In the database, however, the number would be stored like this:

1234.560000 if it’s a currency field, or

1234.56 if it was, for instance, a percentage.

When you send a record or part of a record to either the **revise** or **update** web service methods, you would be expected to send in the data in the format of the user that sends the data in. So for John, he would have to send in ‘1.234,56’ on a currency field to end up with ‘1234.560000’ in the database. When logged in to coreBOS, coreBOS would take care of the correct formatting when John views or edits a record.

But what if John sends in the value in database-format? What if he would send in ‘1234.560000’ for his currency field? Well, coreBOS wouldn’t understand that and try to convert it to the database format anyway. Since John uses the dot as his thousands separator, coreBOS would remove that from the value first, since databases don’t know this concept. Then coreBOS would apply decimals if there weren’t any to start with. CoreBOS would expect those to be indicated with a comma since it knows it’s John that sends in the data.

Now John would end up with the number ‘1234560000.000000’ in the database. In the application, he would see ‘1.234.560.000,00’, which is not what he wanted. So John has to make sure he sends in all currency and number fields in the format he specified in his user preferences.

But, **since 26-07-2018**, he could also do something else. He could add a special flag (or multiple) to his data, that tells coreBOS what to expect. Say John is updating a Potential with this data:

```php
    $input_array =  array (
            'amount' => '1234.56',
            'probability' => '5.00',
            'id' => '5x195784',
    );

    $moduleName = 'Potentials';

    $update = $cbconn->doRevise($moduleName, $input_array);
    ```

Normally, this would go horribly wrong. But if he were to update the
input array with some special fields, it wouldn’t:
```php

    $input_array =  array (
            'amount' => '1234.56',
            'probability' => '5.00',
            'id' => '5x195784',
            '__cbws_skipcurdbconvamount' => 1,
            '__cbws_skipcurdbconvprobability' => 1,
    );
```   

If he were to add the two fields with the name-prefix
**\_\_cbws\_skipcurdbconv** followed by the fieldname that he wants to
send in formatted as database-format, he would get the result he
expected (1.234,56 and 5,00).

But, there’s more. He could also add a single, special flag called
**\_\_cbws\_skipcurdbconvall** (notice the ‘all’ at the end) to make
sure coreBOS treats all his fields as database-formatted.

There is one drawback to using the "all" special flag though, which is
quite obvious: you really need to make sure to input **ALL** data in the
database format. This includes date fields. Basically, setting the "all"
flag forces you to format the record as if you were doing an INSERT or
UPDATE query on the database.

What about inventory lines?
===========================

If you had tried the above examples on an inventory module, you would
notice that would not work. This is because the inventory lines are not
fields, and are not treated as such by coreBOS. To be able to send your
inventory lines with currencies formatted in the database format, you
need to add:

    __cbws_skipcurdbconv_pdo

to your record and set it to anything, like "1" or "true".

This mechanism works completely separate from the ones mentioned before.
If you want to send in your entire inventory record (for instance a
sales order including the inventory lines) in database-format, you would
have to set both **\_\_cbws\_skipcurdbconv\_pdo** and
**\_\_cbws\_skipcurdbconvall** to your record.

<div class="notices blue"> 
<strong>A note:</strong> Do not mistake inventory
lines with the InventoryDetails modules. InventoryDetails is a modern
module that does treat all of its numbers as fields. Setting the
<strong>__cbws_skipcurdbconv_pdo</strong> flag there or on a sales order (for
instance) that does not use the ‘old’ inventory lines mechanism would
not do anything. </div>
<br>
<br>
<div class="notices blue"> 
Thanks [Guido
Goluke](https://github.com/Luke1982)!! </div>


<br>
------------------------------------------------------------------------

[Next](../10.reservedparameter)| Chapter 18: Format and reserved parameter.


------------------------------------------------------------------------