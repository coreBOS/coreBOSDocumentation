---
title: 'coreBOSCP - Known Issues'
metadata:
    description: 'coreBOSCP - Known Issues'
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
        - portal
---
---

## Search doesn't work correctly

Sadly there isn't much I can do here since it is a problem of vtiger CRM REST interface. The problem is that vtiger CRM REST does not support parenthesis in VQL, so when I look for the quotes related to the contact who has logged in (for example), I execute this VQL:

```
select * from quotes where accountid=xx or contactid=yy
```
when we search on quotes, this gets converted to:

```
select * from quotes where accountid=xx or contactid=yy and condition1 and condition2
```

this retrieves all the quotes that belong to the account AND those that fulfill the conditions and belong to the contact. The correct way to do this is:

```
select * from quotes where (accountid=xx or contactid=yy) and condition1 and condition2
```

but we cannot use the parenthesis in VQL, so, short of reprogramming VQL there is nothing better I can do.

I trust this will be fixed in the future.