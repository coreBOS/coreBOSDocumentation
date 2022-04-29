---
title: 'Applications'
metadata:
    description: 'Record all the software applications and appliances you have in your company.'
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

### Fields

#### Information

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
<td>Name</td>
<td>string</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
<tr>
<td>Security Level</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Validate</td>
<td>checkbox</td>
<td></td>
</tr>
<tr>
<td>Destruido</td>
<td>checkbox</td>
<td></td>
</tr>
<tr>
<td>Operating System</td>
<td>picklist</td>
<td>MS-DOS,OS/2,Windows XP Home,Windows XP,Windows Vista,Windows 7,Windows Server 2003,Windows Server 2008,UNIX,GNU/Linux,Novell,Mac OS X,Symbian,Android,BlackBerry,Microsoft .NET</td>
</tr>
<tr>
<td>Data Base</td>
<td>picklist</td>
<td>NO,Microsoft SQL Server,FileMaker,Micrososoft Access,Open Access,Oracle,dBase,BBDD Pick/3D,MySQL,SI</td>
</tr>
<tr>
<td>Remote Access</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Where aplication is executed</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Files aplication accesses</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Time-Out</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Fecha Baja</td>
<td>date</td>
<td></td>
</tr>
</tbody>
</table>

#### Custom Information

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
<td>Function</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Template</td>
<td>relation</td>
<td>Documents</td>
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
<tr>
<td>System</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Manufacture</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>Etiquetas</td>
<td>string</td>
<td></td>
</tr>
</tbody>
</table>

#### Pruebas con Datos Reales

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
<td>Test nº</td>
<td>number</td>
<td></td>
</tr>
<tr>
<td>Date</td>
<td>date</td>
<td></td>
</tr>
<tr>
<td>Security Level Measures</td>
<td>text</td>
<td></td>
</tr>
<tr>
<td>Test Description</td>
<td>text</td>
<td></td>
</tr>
</tbody>
</table>
