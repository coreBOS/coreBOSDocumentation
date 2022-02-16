---
title: 'Update individual fields when importing.'
---

Update individual fields when importing.
========================================

Example of how to use
---------------------

-   First I need a CSV file prepared to import into coreBOS. I will do
    the example with contacts (any other importable coreBOS module works
    the same). To obtain the file I export information from coreBOS demo
    site. This is the image:
-   <img src="/en/import/upsert_export.png" width="500" />
-   This gives me a ![file with a lot of columns and
    rows](/en/import/contacts_raw.csv) of contact information
-   I eliminate most of them for the sake of the example. I am supposing
    that I need to update ONLY the department field of the contact
    without modifying the others. I am going to eliminate most columns
    to make the import file smaller but I am still going to leave some
    columns I do not want to import, just ignore them. So I end up with
    ![this file](/en/import/contacts_update.csv), which has this inside:

<table>
<thead>
<tr class="header">
<th>First Name</th>
<th>Contact Id</th>
<th>Last Name</th>
<th>Mobile</th>
<th>Lead Source</th>
<th>Department</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Mary</td>
<td>CON1</td>
<td>Smith</td>
<td></td>
<td>Trade Show</td>
<td>woanders01</td>
</tr>
<tr class="even">
<td>Patricia</td>
<td>CON2</td>
<td>Johnson</td>
<td>(092) 223-5945</td>
<td>Public Relations</td>
<td>woanders02</td>
</tr>
<tr class="odd">
<td>Linda</td>
<td>CON3</td>
<td>Williams</td>
<td>(105) 252-3316</td>
<td>Employee</td>
<td>woanders03</td>
</tr>
<tr class="even">
<td>Barbara</td>
<td>CON4</td>
<td>Jones</td>
<td>(882) 828-0165</td>
<td>Other</td>
<td>woanders04</td>
</tr>
<tr class="odd">
<td>Elizabeth</td>
<td>CON5</td>
<td>Brown</td>
<td>(633) 076-5365</td>
<td>Trade Show</td>
<td>woanders05</td>
</tr>
<tr class="even">
<td>Jennifer</td>
<td>CON6</td>
<td>Davis</td>
<td>(690) 300-7311</td>
<td>Existing Customer</td>
<td>woanders06</td>
</tr>
<tr class="odd">
<td>Maria</td>
<td>CON7</td>
<td>Miller</td>
<td>(903) 226-7361</td>
<td>Other</td>
<td>woanders07</td>
</tr>
<tr class="even">
<td>Susan</td>
<td>CON8</td>
<td>Wilson</td>
<td>(738) 571-9515</td>
<td>Word of mouth</td>
<td>woanders08</td>
</tr>
<tr class="odd">
<td>Margaret</td>
<td>CON9</td>
<td>Moore</td>
<td>(201) 799-4322</td>
<td>Employee</td>
<td>woanders09</td>
</tr>
<tr class="even">
<td>Dorothy</td>
<td>CON10</td>
<td>Taylor</td>
<td>(348) 842-2559</td>
<td>Direct Mail</td>
<td>woanders10</td>
</tr>
<tr class="odd">
<td></td>
<td>CON11</td>
<td>sd</td>
<td></td>
<td>--None--</td>
<td>woanders11</td>
</tr>
<tr class="even">
<td>marco</td>
<td>CON12</td>
<td>deluca</td>
<td></td>
<td>--None--</td>
<td>woanders12</td>
</tr>
<tr class="odd">
<td></td>
<td>CON13</td>
<td>iLabs Demos</td>
<td></td>
<td></td>
<td>woanders13</td>
</tr>
</tbody>
</table>

-   Note that I have eliminated most columns except the ones I need to
    do the matching for update and the ones I want to ignore for the
    sake of the example. I have modified all the departments.
-   Now I import as you normally would in coreBOS. I map ONLY the fields
    I want to be updated **and the mandatory fields** of the import
    (usually the ones you are going to be merging on), all the others
    are directly ignored. I select automerging, update and indicate the
    criteria for matching.
-   <img src="/en/import/upsert_import.png" width="600" alt="upsert import" />
-   Before and After images:

**Before update List View**  
<img src="/en/import/before_upsertlv.png" class="align-center" alt="Before update List View" />  
  
**Before update Detail View**  
<img src="/en/import/before_upsertdv.png" class="align-center" alt="Before update Detail View" />  
  
**After update List View**  
<img src="/en/import/after_upsertlv.png" class="align-center" alt="After update List View" />  
  
**After update Detail View**  
<img src="/en/import/after_upsertdv.png" class="align-center" alt="After update Detail View" />  
