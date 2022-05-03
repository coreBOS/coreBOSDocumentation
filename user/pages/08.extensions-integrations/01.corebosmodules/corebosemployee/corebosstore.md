---
title: 'coreBOS Employee Module'
metadata:
    description: 'Employee module for coreBOS'
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

### How it works
This is a normal vtlib module which can be installed through the module manager. It contains a set of fields and information about your employees. The assigned to field can be linked to the user accessing the application as a means to extend the information we have about each employee that has access to coreBOS, but it is not really linked in any special way.

===

### Fields

#### Relationship Information

<table class="table table-striped">
<thead>
<tr class="header">
<th>Field</th>
<th>Type</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr>
<td>Employee No</td>
<td>4</td>
<td></td>
</tr>
<tr>
<td>SSN</td>
<td>1</td>
<td></td>
</tr>
<tr>
<td>Name</td>
<td>1</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>ID</td>
<td>1</td>
<td></td>
</tr>
<tr>
<td>Situation</td>
<td>1</td>
<td></td>
</tr>
<tr>
<td>Marital Status</td>
<td>1</td>
<td></td>
</tr>
<tr>
<td>Category</td>
<td>1</td>
<td></td>
</tr>
<tr>
<td>numchildren</td>
<td>7</td>
<td></td>
</tr>
<tr>
<td>User</td>
<td>52</td>
<td></td>
</tr>
<tr>
<td>People in charge of</td>
<td>7</td>
<td></td>
</tr>
<tr>
<td>Birth Date</td>
<td>5</td>
<td></td>
</tr>
<tr>
<td>Birth Place</td>
<td>1</td>
<td></td>
</tr>
<tr>
<td>Age</td>
<td>7</td>
<td></td>
</tr>
<tr>
<td>Assigned To</td>
<td>53</td>
<td></td>
</tr>
<tr>
<td>Created Time</td>
<td>70</td>
<td></td>
</tr>
<tr>
<td>Modified Time</td>
<td>70</td>
<td></td>
</tr>
</tbody>
</table>
<br>
#### Employment Information

<table class="table table-striped">
<thead>
<tr class="header">
<th>Field</th>
<th>Type</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr>
<td>Yearly Compensation</td>
<td>1</td>
<td></td>
</tr>
<tr>
<td>Type of Contract</td>
<td>1</td>
<td></td>
</tr>
<tr>
<td>Hourly Compensation</td>
<td>1</td>
<td></td>
</tr>
<tr>
<td>Departament</td>
<td>1</td>
<td></td>
</tr>
<tr>
<td>Joined Company on</td>
<td>5</td>
<td></td>
</tr>
</tbody>
</table>
<br>
#### Contact Information

<table class="table table-striped">
<thead>
<tr class="header">
<th>Field</th>
<th>Type</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr>
<td>Address</td>
<td>21</td>
<td></td>
</tr>
<tr>
<td>Personal Phone</td>
<td>11</td>
<td></td>
</tr>
<tr>
<td>City</td>
<td>1</td>
<td></td>
</tr>
<tr>
<td>Cell Phone</td>
<td>11</td>
<td></td>
</tr>
<tr>
<td>State</td>
<td>1</td>
<td></td>
</tr>
<tr>
<td>Work Phone</td>
<td>11</td>
<td></td>
</tr>
<tr>
<td>Postal Code</td>
<td>1</td>
<td></td>
</tr>
<tr>
<td>Personal Email</td>
<td>13</td>
<td></td>
</tr>
<tr>
<td>LinkedIn Profile</td>
<td>17</td>
<td></td>
</tr>
<tr>
<td>Work Email</td>
<td>13</td>
<td></td>
</tr>
<tr>
<td>Twitter Profile</td>
<td>17</td>
<td></td>
</tr>
<tr>
<td>Skype ID</td>
<td>85</td>
<td></td>
</tr>
<tr>
<td>Facebook Profile</td>
<td>17</td>
<td></td>
</tr>
<tr>
<td>GTalk ID</td>
<td>1</td>
<td></td>
</tr>
</tbody>
</table>
<br>
#### Studies Information

<table class="table table-striped">
<thead>
<tr class="header">
<th>Field</th>
<th>Type</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr>
<td>High School</td>
<td>1</td>
<td></td>
</tr>
<tr>
<td>High School Graduation Year</td>
<td>1</td>
<td></td>
</tr>
<tr>
<td>High School GPA</td>
<td>1</td>
<td></td>
</tr>
<tr>
<td>High School Comments</td>
<td>21</td>
<td></td>
</tr>
<tr>
<td>Undergraduate School</td>
<td>1</td>
<td></td>
</tr>
<tr>
<td>Undergraduate School Graduation Year</td>
<td>1</td>
<td></td>
</tr>
<tr>
<td>Undergraduate School GPA</td>
<td>1</td>
<td></td>
</tr>
<tr>
<td>Undergraduate Comments</td>
<td>21</td>
<td></td>
</tr>
<tr>
<td>Postgraduate Degree/School</td>
<td>1</td>
<td></td>
</tr>
<tr>
<td>Postgraduate School Graduation Year</td>
<td>1</td>
<td></td>
</tr>
<tr>
<td>Postgraduate School Graduation Year</td>
<td>1</td>
<td></td>
</tr>
<tr>
<td>Postgraduate Degree School GPA</td>
<td>1</td>
<td></td>
</tr>
<tr>
<td>Postgraduate Comments</td>
<td>21</td>
<td></td>
</tr>
</tbody>
</table>
<br>
#### Custom Information
<br>
#### Additional Information

<table class="table table-striped">
<thead>
<tr class="header">
<th>Field</th>
<th>Type</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr>
<td>Description</td>
<td>19</td>
<td></td>
</tr>
</tbody>
</table>