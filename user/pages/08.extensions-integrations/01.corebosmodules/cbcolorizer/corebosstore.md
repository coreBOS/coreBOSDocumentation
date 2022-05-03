---
title: 'Color and Condition Fields and Blocks Extension'
metadata:
    description: 'This extension permits you to establish different coloring and formatting rules for fields on a module depending on conditions based on the values of the fields in the record. You can also manipulate blocks by closing and hiding them depending on field conditions defined.'
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

This extension permits you to establish different coloring and formatting rules for fields on a module depending on conditions based on the values of the fields in the record. You can also manipulate blocks by closing and hiding them depending on field conditions defined.

===

### Documentation

+ Open the extension's Administration page by going to **Settings** → **Module Manager** → **Colorizer** → **Configuration** (hammer icon)

![Colorizer1](cbcolordoc01.png?width=100%)

+ Choose the module and field you want to format

![Colorizer2](cbcolordoc02.png?width=100%)

+ You can define different conditions, which must be true to apply the field formating selected

![Colorizer3](cbcolordoc03.png?width=100%)

+ You have to define the format settings separately for field and label
 - Background color, Text color,Border color, Blink feature accept a hex value of the color.
 - Font weight accepts only the value bold
 - Font accepts a name of a Font, which must be available in the browser
 - Alignment accepts left, right or center
 - Save each line clicking on the SET button

![Colorizer4](cbcolordoc04.png?width=100%)

![Colorizer5](cbcolordoc05.png?width=100%)

+ If you have set all formatting options, it should look something like the next image:

![Colorizer6](cbcolordoc06.png?width=100%)

+ Additionally each Condition can launch different Actions like collapse, expand or hide a complete block
 - If you want to delete an action, click on choose action. These entries will be removed!

![Colorizer7](cbcolordoc07.png?width=100%)

+ After you save the configuration with the Save Button, you should view your settings on top

![Colorizer8](cbcolordoc08.png?width=100%)

### Check Reference Fields
If you need to create conditions on reference fields, which contain references to other modules, you have to follow special rules.

To check if a value is present and a link exists to any given module do this:

+ Field: related_to
+ Operation: contains
+ Value: module={ModuleName} for example: module=Accounts

To check if a specific Record ID is linked inside such field:

+ Field: related_to
+ Operation: contains
+ Value: record=1234

As you may notice, these are parts from the URL of the linked record. This means that, in the background, this extensions replaces the content of the field with the complete Detail View Link and searches on that value.

### BBCode
You can enable the usage of BBCode for every field, regardless of it's type.

All supported BBCodes can be used to format the text.

Examples:
```[url]http://www.domain.com[/url] – URL in every field
[url=http://www.domain.com]link to Domain[/url] - -URL with special label
[img]http://www.domain.com/path/to/image.jpg[/img] - Image
[img width=50 height=10]http://www.domain.com/path/to/image.jpg[/img] – resized image, linked to the original
[b]bold text[/b]
[youtube]VideoID[/youtube]
[email]receiver@domain.com[/email]
```

### Special Customization::Setup of dynamically changed formatting
If you want to see any formatting changes happen directly after changing a value in DetailView, you have to add one line of code to the include/js/dtlviewajax.js file as can be seen in the next patch.

```js
diff --git a/include/js/dtlviewajax.js b/include/js/dtlviewajax.js
index d0f9222..85c941a 100644
--- a/include/js/dtlviewajax.js
+++ b/include/js/dtlviewajax.js
@@ -289,6 +289,7 @@ function dtlViewAjaxFinishSave(fieldLabel,module,uitype,tableName,fieldName,crmI
                                        if(getObj(dtlView) != null) getObj(dtlView).innerHTML = "";
                                        if(getObj("comments") != null) getObj("comments").value = "";
                                }
+                                if (typeof colorizer_after_change === "function") { colorizer_after_change(fieldName, tagValue); }
                                document.getElementById("vtbusy_info").style.display="none";
                        }
                }
```