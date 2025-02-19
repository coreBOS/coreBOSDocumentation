---
title: 'Making of the Generic Master-Detail Editor'
metadata:
    description: 'Access any saved menu structure using this business map.'
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
        - businessmappings
        - adminmanual
    tag:
        - editor
---

Some years ago we created a master-detail business map for coreBOS, but it was mainly for use in external applications. It could be used to \[enhance the fields in the native inventory modules\], but there was no way of easily creating a row-based editor between two modules with this relation. This situation changed last month of April 2021 with the arrival of the first version of a native developer block that uses the master-detail business map.

Let's comment first on some of the features that coreBOS has acquired while implementing the functionality.

### Quick edit

The initial plan was to use the quick edit popup to do the editing of the lines. For that to work, we needed to be able to define the fields to show in the popup independently of the fields configured in the layout editor, so we refactored the code to support a list of fields to show. This works by loading the fields into the [$QCFIELDS\_QUERY variable and including the quick create code.](https://github.com/tsolucio/corebos/blob/master/include/quickcreate.php#L20)

### Detail view popup

Once we had the Quick create edit screen we fixed the detail view popup window support (adding the edit view popup parameter in the URL). Hiding some more buttons and other elements. To such an extent that it looks really curious inside a div element.

The parameters is **Module\_Popup\_Edit=1**

![](detailviewinsidediv.png?width=100%)

The instruction to load that div looks like this

```php
masterdetailwork.MDView('mdgridprojectprojecttask', 'ProjectTask', 44570);
```

### Edit view popup

Reached this point, and after some testing, the quick create approach didn't seem like the right solution so we enhanced the edit popup window with the functionality to define the set of fields we want to edit (just like we did for the quick create).

The parameters is **FILTERFIELDSMAP**

### Default values

The next thing we ran into was the missing values. Both in the quick create and the restricted popup edit screen, all the fields that were not present stayed, logically, empty. So we made a change to load the default values of fields that are not given in quick create, web service, and the popup edit screen. This enhanced the internal field cache structure and checked a long-standing request from our to-do list.

### Toast-UI grid support

The last step before implementing the actual developer block was to upgrade the Toast-UI grid library that we are starting to use everywhere in coreBOS and add some generic list view type code to make it easier to work with this library.

### Developer block

Finally, we enhanced the business map with some other features and implemented the native master-detail functionality which you can learn about [reading the official documentation](../../../05.configuration-tools/02.business-maps/19.masterdetailmapping) and watching the video presentation

<iframe width="542" height="261" src="https://www.youtube.com/embed/pb05jH-HeBA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>