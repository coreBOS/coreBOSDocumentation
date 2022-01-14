---
title: 'List Columns'
---

List Columns
============

The purpose of this mapping is to override the predefined columns that
appear on the related and popup lists for a module. Each module has two
hard coded lists of columns, one defines the columns that are showed
when the module is on a related lists (list\_fields) and the other
defines the columns that are shown in the module's popup capture screen
(search\_fields). Many times we want to be able to change these columns
because the default ones aren't important for us or some users need more
information in the popup screen. Using the List Columns mapping you can
adapt these lists to your requirements without modifying the code.

The accepted format is:

     <map>
      <originmodule>
        <originid>22</originid>  {optional}
        <originname>{ModuleName}</originname>
      </originmodule>
      <relatedlists>
       <relatedlist>
       <module>{parentmodule}</module>
       <linkfield></linkfield>
        <columns>
         <field>
          <label></label>
          <name></name>
          <table></table>  {optional}
          <columnname></columnname>  {optional}
         </field>
         ...
        </columns>
       </relatedlist>
       ....
      </relatedlists>
      <popup>
        <linkfield></linkfield>
        <columns>
         <field>
          <label></label>
          <name></name>
          <table></table>  {optional}
          <columnname></columnname>  {optional}
         </field>
         ...
        </columns>
      </popup>
     </map>

where we can define a different set of columns per related lists and one
for the popup screen.

The name of the mapping must be **{ModuleName}\_ListColumns** and the
name of the global variable, if you need it to be per user, would be:
**BusinessMapping\_{ModuleName}\_ListColumns**

The way to understand this map is like this:

&lt;WRAP center round box 80%&gt; this Potentials\_ListColumns map is
for Potentials lists, when you show a list of potential records, in the
Contacts module I want you to show these columns, when you show that
list in Accounts I want you to show these others,... when you open a
popup to select a potential record I want you to show these

so, all the field references must be fields that are on the Potentials

if you want to change how contacts appear in their lists then you have
to create a Contacts\_ListColumns and open a related list section for
Potentials &lt;/WRAP&gt;

&lt;WRAP center round info 80%&gt; If you need to modify the columns
that appear in the Global Search for the module, create a section where
parentmodule is set to **Utilities**. &lt;/WRAP&gt;
