---
title: 'coreBOS Geographic Map'
metadata:
    description: 'An extension that will permit us to geolocalize our clients, potentials, tickets or any module with an address using Google Maps or OpenStreetMaps integration.'
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
        - geolocation
        - coordinates
---

An extension that will permit us to geolocalize our clients, potentials, tickets or any module with an address using Google Maps or OpenStreetMaps integration.

===

### coreBOSCRM GeoLocalization Map extension

The **coreBOSCRM GeoLocalization Map** extension will permit you to locate your clients on a map, searching by different criteria, making programming a route of sales visits, localizing a technician to send to an emergency, or simply finding a set of potential clients for a campaign an easy task.

This is a list of some of the features of the extension:

- Map is **automatically centered** at the current user's location based on browser information (not always available nor exact), if this information can't be find it will be centered on the user's address which can be found in his "Preferences" page. This makes disperse sets of sales people able to quickly search upon their location. Finally, if none of the previous information is available the map will be centered on the company's address information located in Settings. This point in the map will be marked with a special icon.
- A **tabbed view** of **different search options** will permit us to easily launch searches based on existing filters, for accounts, contacts, leads, trouble tickets and events.
- **Supports radius search**, whereas you define a point in the map and the circle radius around which you want to see the included records.
- Different icons mark the different filters applied, because filters can be accumulated
- **Overlapping check**. When a record overlaps because they have the same geoposition (for example, two accounts in the same office building), the application introduces a small offset so the markers on the map don't overlap completely
- The set of **results is shown in a grid list** (using [slickgrid](https://github.com/mleibman/SlickGrid)) where they can be grouped by entity type, quickly located in the map by clicking on the target icon or access the full record by clicking on the name of the located record
- Clicking on any marker will **popup an information window** indicating the details of the record at that position and permitting a series of actions:
- **Reload coordinates**, in case the address information has changed
- **Driving directions** from your current location to the entity
- A radius search can be launched around the record which will, not only show us a circle with the extent of the search but also a **list of all the records and open trouble tickets located** inside the circle
- **Default options** for radius search and default tab, among others can be set per user.
- **GeoLocalization information fetched with cron.** A special cron service executed once a day will automatically retrieve geoposition information of new accounts, contacts and leads, and also update those whose address information has changed and eliminate the information of those that have been deleted.
- Simple migration process from previous version.

[Youtube video presentation](https://www.youtube.com/watch?v=4MB8K-dkpOo&list=PL0oN2FI_W55zX7MCNFVW1mF1HBtNPUCbo)

Let's look into some of these features in detail.

### Filter Tab

The options in this search tab will permit us to select any combination of existing filters available for each of the three supported modules and have the values marked on the map.

If more than one filter is selected each filter will have a different colored marker and those entities that appear in more than one filter will have their own special colored marker. On the upper right panel of the map section you will find a legend with the different colors assigned.
![Map1](evvtmap01.png?width=100%)

**As an additional helper** for searching on the modules, each filter set is followed by a user select box which shows all the subordinated users of the currently logged in user. If a user is selected this condition is **ADDED** to the selected filters, so they will only show the records that fulfill the filter AND belong to the selected user. This makes it easy to select those records assigned to oneself or to anther given user without having to create specific filters.

### Ticket Tab

The ticket tab will permit us to search for account and contacts associated to trouble tickets. As with the filter tab we are presented with a set of filters that exist on the trouble ticket entity and we can select one or more to have the associated accounts and contacts marked on the map. Also, we find a user capture box where we can restrict the trouble tickets, not only to the conditions of the selected filter but also of the chosen user.

With this setup, for example, we could easily create a filter with open tickets to visit "today" (which would be a custom field) and then search the accounts and contacts that any given user has to see in one day. This is the use case that produced this tab, whereas a company needs to know which technician is around a certain area when an emergency arises.
![Map2](evvtmap02.png?width=100%)
In this scenario, the technician himself could enter the application. The map extension will automatically center on his position and he could select the new ticket on the map and ask for driving directions with just a few clicks:

![Map3](evvtmap03.png?width=100%)

### Events/Visits Tab

This tab is for searching the calendar events. With the different options available we will be able to select a date range and a user to have all those accounts, contacts and leads associated to that user with an event in the selected date range marked on the map.

We can also indicate the entities we want to have shown by clicking on the checkboxes.

This is an easy and powerful way to search for additional clients to visit on certain days that the agenda needs filling. Once you have located some of the clients you can execute an adhoc radius search to see if there is anybody else you could go and visit.

### Radius Tab

The direct radius search will permit us to find a set of accounts, contacts and leads within a certain circle centered on any latitude and longitude given. Thus the parameters for the search are exactly those: latitude, longitude and radius of the circle. Since the normal situation will be to center the circle on some given entity, we have added an entity capture. If any entity is selected and the latitude and longitude fields are empty, the system will use the coordinates of the selected entity. We have also added a quick capture button with which the user will be able to fill in the latitude and longitude fields using the entity and then adjust accordingly if necessary.
![radiusgroupby](evvtmapradiusgroupby.png?width=100%)

### adhoc Radius Search and More Information

Each marker can be clicked on to obtain a set of information about the entity positioned there. This popup window will contain the name, address and contact information and some action links to work on:

- Direction: this action will give us automatic driving directions from our current position to the entity. These directions will be shown in the directions tab situated on the right panel and the affected area in the map will be centered.
- Reload Coordinates: this will force the application to eliminate cached information about this entity and retrieve updated positioning from the current address information on record
- Draw Circle: this will permit us to execute an adhoc radius search around the selected record. A popup window will automatically appear with information of all entities contained inside the circle with open trouble tickets also shown and permitting to click on any one of them to have them open in full detail view of the record
- Clear circle: will undo the current radius search
![radiusinfo](evvtmapadhocradiusinfo.png?width=100%)

### Results Tab

The set of **results is shown in a grid list** in the right panel, inside the results tab. At the top of the tab we see the full count of results found followed by the grouping option and finally the list of all the records found.

The results tab is based on [slickgrid](https://github.com/mleibman/SlickGrid). This powerful javascript library permits us to easily page through the results seeing their name and entity type. It will permit us to group the records by entity type and quickly located any record on the map by clicking on the target icon, or access the full record by clicking on the name of the located record. There is a screen shot with grouping in the [Radius Tab](../../01.corebosmodules/cbgeomap/id:981b5eabfacc1227db2444a721cb8ad3/store:corebosmodule#radiusmap) section

Finally, clicking on the name of the entity will take us to it's detail view inside vtiger CRM.

### Preferences Tab

This tab gives us access to a few variables that we can set on a per user basis. The variables are:

- Default Radius: will be the value used by default in both the Radius search and the adhoc radius search
- Default Zoom Size: this will be the initial zoom size of the map on first load. The default value is 7
- Default Map Type: which will permit the user to select between the satellite or map view
- Default Tab: this defines the default search tab of the extension for each user, so they can set the one they use the most.

### Geo Position Information Cache and Update

The extension will silently look for the geo position of any record it needs to mark on the map and cache this information forever. All subsequent searches for this record will be read from the cache and never looked up again. This is rather drastic but acceptable in general as it is rare for a company to change their address.

To attend to those situations where a company does change their address and for the situation of new entities that have been created in the application we have created a cron service that will be executed once a day and that will do three tasks:

- update all position information of those records that have been modified since that last execution. With this we guarantee the use of valid and updated positioning for the changed entities
- adds new positioning information for new records
- deletes information of deleted records
In other words, thanks to the cron service we can basically forget about the state of the information as it will take care of itself.

This service is automatically installed and configured during the normal installation of the extensions, so all you have to do to get it working is have the base vtiger CRM cron service executed every 15 minutes.

I would like to thank [Alan Lord of Libertus](https://libertus.co.uk/) for sharing his code as it was a sort of template for us when we got to that point of our development.

### Migration from previous version

We have basically rewritten the whole extension, converting it into an extension and not a module, following vtiger CRM programming guidelines for database access and security, cleaning up the code and adding new user interface and functionality.

In this process we have changed the internal name of the extension and the database tables used to avoid conflict with the open source version of this extension. If you have either the open source version or our previous version you must execute the migration script to copy the geo position data into the new structure.

This is one simple command that must be executed in the browser like this:

```
http://your_server/your_vtigercrm/index.php?module=evvtMap&action=migrate
```

### Roadmap and Todo

- Restricted values shown in more information popups to the active filter conditions
- Add more preferences options (default center on, …)
- Search on other entities. For example, invoices to see pending invoices by region or radius
- Sync results and map in both directions, now it only works from grid to map, selecting a marker does not select the row in the grid
- Add support for searching on the grid
- Link records found to a campaign

### Prices

This extension is on sale at SIMPLE & LIBRE - VTIGER CRM, [Géolocalisation des prospects avec filtrage et sélection autour de "xxx" kms](http://www.simple-et-libre.com/geolocalisation-des-prospects-avec-filtrage-et-selection-autour-de-xxx-kms/) and directly from us

### Further development

This extension is in continuous development with changes to adapt to different requirements of our clients and we are very comfortable with the technology so contact us with your needs and we will do our best to help you.

We are currently developing a new tab for a real estate company, where they will be able to launch a radius search centered on a certain location a client is looking for apartments with certain conditions that the apartments must fulfill. These apartments are products, once we find them we locate them on the map.