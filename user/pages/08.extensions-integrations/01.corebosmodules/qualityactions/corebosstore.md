---
title: 'Quality Actions module'
metadata:
    description: 'This module is related with Quality Claims module and details the diferent actions or steps taken to resolve or attend the quality claim.'
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

This module is related with [Quality Claims module](../../01.corebosmodules/qualityclaims/id:414901aa79ca8a68ffcfad4da662d4ee/store:corebosmodule) and details the diferent actions or steps taken to resolve or attend the quality claim.

===

### Fields

#### Quality Actions Information

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
<td>Product</td>
<td>relation</td>
<td>Products</td>
</tr>
<tr>
<td>Quality Claim</td>
<td>relation</td>
<td>QualityClaims</td>
</tr>
<tr>
<td>Product Code</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Action Status</td>
<td>picklist</td>
<td>--None--</td>
</tr>
<tr>
<td>Product Description</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>QC Actions N</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
</tr>
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
