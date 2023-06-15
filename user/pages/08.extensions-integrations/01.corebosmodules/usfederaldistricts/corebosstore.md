---
title: 'US Federal Districts'
metadata:
    description: 'Module to record US Federal Districts'
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

Module to record US Federal Districts

===

### Fields

#### U.S. Federal Districts Information

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
<td>US District Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Record No</td>
<td>autonumber</td>
<td></td>
</tr>
<tr>
<td>Citation</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>US Court of Appeals Circuit</td>
<td>relation</td>
<td>USAppealsCourtCircuit</td>
</tr>
<tr>
<td>No of Judges</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Chief Judge Name</td>
<td>string</td>
<td></td>
</tr>
</tbody>
</table>
<br>
#### U.S. District Divisions and Sub-divisions

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
<td>Division-Subdivision 1</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Division-Subdivision 2</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Division-Subdivision 3</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Division-Subdivision 4</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Division-Subdivision 5</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Division-Subdivision 6</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Division-Subdivision 7</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Division-Subdivision 8</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Division-Subdivision 9</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Division-Subdivision 10</td>
<td>string</td>
<td></td>
</tr>
</tbody>
</table>
<br>
#### Custom Information
<br>
#### Description

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
<td>text</td>
<td></td>
</tr>
</tbody>
</table>
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
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
<tr>
<td>Created Time</td>
<td>datetime</td>
<td></td>
</tr>
<tr>
<td>Modified Time</td>
<td>datetime</td>
<td></td>
</tr>
</tbody>
</table>
