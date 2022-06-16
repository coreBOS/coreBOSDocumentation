---
title: 'Language Skill'
metadata:
    description: 'Language Skills module to register information about the languages spoken by your employees and contacts.This is part of the Attorneys Back Office Human Resources extensions.'
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
---
Language Skills module to register information about the languages spoken by your employees and contacts.
This is part of the **Attorney's Back Office Human Resources** extensions.

===

### Fields

#### LanguageSkill Information

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
<td>Related to</td>
<td>relation</td>
<td>Attorneys,Managers,Paralegals,Secretaries,SupportPersonnel,
Procurador</td>
</tr>
<tr>
<td>Language</td>
<td>picklist</td>
<td>--- Please Select ---,Albanian,Amharic,Arabic,Armenian,
Azerbaijani,Belorussian,Bengali,Bulgarian,Chinese (Cantonese),
Chinese (Mandarin),Croatian,Czech,Danish,Dari,Dutch,English,
Estonian,Finnish,French,Georgian,German,Greek,Hebrew,Hindi,
Hungarian,Indonesian,Italian,Japanese,Kazakh,Khmer,Kirgiz,
Korean,Kurdish,Laotian,Latvian,Lithuanian,Macedonian,Malay,
Moldovan,Mongolian,Norwegian,Persian,Polish,Portuguese (Brazilian),
Portuguese (Classical),Pushtu,Romanian,Russian,Serbian,
Spanish,Swedish,Tagalog,Tajik,Tamil,Thai,Turkish,Ukrainian,
Urdu,Uzbek,Vietnamese</td>
</tr>
<tr>
<td>Language Fluency</td>
<td>multipicklist</td>
<td>--- Please Select ---,Read,Write,Read+Write,Comprehend,Speak,Proficient</td>
</tr>
<tr>
<td>Language Competency</td>
<td>multipicklist</td>
<td>--- Please Select ---,Listening,Reading,Writing,Speaking</td>
</tr>
</tbody>
</table>
<br>
#### Custom Information
<br>
#### Comments

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
<td>Language Skill Reference</td>
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
