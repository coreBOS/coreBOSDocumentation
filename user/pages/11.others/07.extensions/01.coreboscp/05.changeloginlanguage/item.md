---
title: 'coreBOSCP::How to change Login page language'
metadata:
    description: 'coreBOSCP::How to change Login page language'
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

```
index d86e387..ae7ad4c 100644
--- a/protected/controllers/SiteController.php
+++ b/protected/controllers/SiteController.php
@@ -167,6 +167,7 @@ class SiteController extends Controller
                $this->layout = "login";
 
                // Languages
+         Yii::app()->session->add('language', 'fr_fr');
                $availableLanguages = glob('protected/messages/??_??');
                $currentLanguage = Yii::app()->getLanguage();
 
```