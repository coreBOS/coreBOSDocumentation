---
title: 'Research Request module'
metadata:
    description: 'Module to control research or investigation requests, used, for example, to document quote analysis requests or the study of possible solutions to problems that appear in the business. This module is related with Research Request Actions module where each exact step is recorded.'
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

Module to control research or investigation requests, used, for example, to document quote analysis requests or the study of possible solutions to problems that appear in the business. This module is related with [Research Request Actions module](../../01.corebosmodules/researchrequestactions/id:bc9024396093031d695ffca92cb7606a/store:corebosmodule) where each exact step is recorded.
 
===

### Fields

#### Research Request Information

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
<td>Account Name</td>
<td>relation</td>
<td>Accounts</td>
</tr>
<tr>
<td>Research Request No</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Member of</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Title</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Related Entity</td>
<td>relation</td>
<td>Project,HelpDesk</td>
</tr>
<tr>
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
<tr>
<td>Product</td>
<td>picklist</td>
<td>--None--</td>
</tr>
<tr>
<td>Priority</td>
<td>picklist</td>
<td>--None--</td>
</tr>
<tr>
<td>Type</td>
<td>picklist</td>
<td>--None--</td>
</tr>
<tr>
<td>Contract Type</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Filial</td>
<td>picklist</td>
<td>--None--</td>
</tr>
<tr>
<td>Location Technique</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Distributor</td>
<td>picklist</td>
<td>--None--</td>
</tr>
<tr>
<td>Request Date</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Finish Date</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Department</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Status</td>
<td>picklist</td>
<td>Creado,En espera,Rechazado,Anulado,Cerrado</td>
</tr>
<tr>
<td>Responsible</td>
<td>picklist</td>
<td>--None--</td>
</tr>
<tr>
<td>Total Time</td>
<td>string</td>
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
