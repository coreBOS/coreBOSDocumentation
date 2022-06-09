---
title: 'coreBOSApps User Guide'
metadata:
    description: 'coreBOSApps User Guide'
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
        - coreBos
    tag:
        - guide
---

From the users point of view the coreBOSApps extension is very simple to
use as it is really an infrastructure to make it easy for developers to
offer simple solutions, encapsulated in windows. Each of these
applications will have their own functionality and user requirements,
which each user will have to learn to get the most out of the
coreBOSApp.

So here we will be talking about the base functionality and user
experience that is needed to work with the coreBOSApps extension.

Accessing coreBOSApps is just like accessing any other coreBOS module,
clicking on the menu link that can be found in Analytics will take us to
the coreBOSApps Canvas. On the canvas we will find a header toolbar with
three options: **Windows**, **Dashboard** and **Applications**. This
toolbar permits us to change the view between the three different views,
establish the default view using the small yellow icon on top of each
option and also minimize the toolbar or the whole coreBOS top menu
section.

![](cbapps_topbar_en.png?width=100%)

### Windows

An ordered list of coreBOSApp icons. Each icon represents an individual
application.

Hovering the mouse over any icon will show us a short description of the
intended functionality of the coreBOSApp.

All the icons, can be sorted by simply dragging the icon to the desired
position.

Clicking on the icon of the coreBOSApp will open a window, within which
we will be able to see the execution of the coreBOSApp. Each window has
a series of base functionality. They can be resized and moved. Most will
have a refresh button to execute the coreBOSApp again without having to
close and open the window, and some will also have an edit button that
will open an additional window with setting options that will affect the
behavior of the coreBOSApp. Both the contents of the coreBOSApp and of
it's related edit settings window are totally dependent on the
functionality of the coreBOSApp.

Some windows can be instantiated, that is executed or opened more than
once, so that the user can configure each one independently from the
others although the base functionality is the same. To accomplish this
we must **press and hold the CONTROL button** while clicking open the
coreBOSApp.

![](cbapptitlebarbuttons.png?width=100%)

Each user will be able to order and position his windows to his likings
and the configuration will be saved so when he returns he will find all
in it's place.

### Dashboard

A view where we can divide the canvas in boxes fixed to the browser and
within which each application runs. We distribute the sections in rows
and columns defining characteristics such as size, status and
application to execute within each frame.

![](cbapps_dashboardedit.png?width=100%)

![](cbappdb.png?width=100%)

### Applications

A view where each application will have the whole canvas to run in and
where we go from one application to the next by clicking on the side
buttons.

On the top right coreBOSApps toolbar there is an icon identifying the
running application and also a drop down with an index of all
applications to jump quickly to any of them.

![](cbapps_topbarapps_en.png?width=100%)

### Special coreBOSApps

There are two special coreBOSApps that are installed by default and
cannot be deleted. These are the coreBOSApps Shop and the coreBOSApps
Configurator, which will help us install and configure permissions on
the installed coreBOSApps.

#### coreBOSApps Shop. Install and Update.

\*\* FIXME \*\*

#### coreBOSApps Configurator

This coreBOSApp permits administrative users to set certain parameters
for each coreBOSApp and user. Initially only the admin users of coreBOS
have access to the configuration coreBOSApp, but an admin user can grant
access to this coreBOSApp to any user and they will be able to affect
the configuration of any other user. For each user we can establish
these variables:

<table class="table table-striped">
<td>Open (on start)</th>
<td>If a window will be open by default when accessing the coreBOSApp extension. If true, the coreBOSApp will be opened and launched automatically when the user opens coreBOSApps. Each user can change this value by closing the window when they configure their canvas. If the Hide variable is set to false and this one to true, the user will not be able to close the window and it will always be open.</td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Enabled</td>
<td>If false the user will not see this coreBOSApp, it will be as if it weren't installed.</td>
</tr>
<tr class="even">
<td>Show</td>
<td>If false the user will not be able to open the window, only see the icon. This could be useful to simply show an icon on the canvas, but also can be used to dynamically change the icon on certain event based on time or on the results of another coreBOSApp running in another window</td>
</tr>
<tr class="odd">
<td>Hide</td>
<td>If false the user will not be able to close the window</td>
</tr>
<tr class="even">
<td>Write</td>
<td>If false the user will not have access to the Edit option of the coreBOSApp</td>
</tr>
</tbody>
</table>

Only administrative users can **delete and install** coreBOSApps. Once a
coreBOSApp has been eliminate it cannot be recovered. You would have to
install it again. coreBOSApps can be hidden for certain users by the
administrator using the coreBOSApps Configurator.

Modifying and saving values is straight forward in the coreBOSApp
window.

Developers Guide and Other Resources
------------------------------------

- [coreBOSApps Developers Guide](http://localhost/coreBOSDocumentation/others/corebosapps_guide)
- [coreBOSApps Reference for Developers](http://localhost/coreBOSDocumentation/others/corebosapps_reference)
- [The Design :-)](https://discussions.corebos.org/documentation/lib/exe/fetch.php?media=corebosapps:cbappsdesign.jpg)

Disclaimer
----------

coreBOSApps does not pretend to be a secure environment, we do not
impose any restrictions on the coreBOSApp possibilities, just as anyone
can send you a coreBOS module that you can install in your coreBOS and
have it do anything to your information, also a coreBOSApp has full
access to all the information contained inside your coreBOS and the
coreBOSApp can do anything with it. Although we will strive to evaluate
and respond to all suspicious code conducts we probably won't have time
to go through all the code of all the coreBOSApp, so the full
responsibility of the acts of any coreBOSApp is beyond our control. You
will install coreBOSApps at your own risk.
