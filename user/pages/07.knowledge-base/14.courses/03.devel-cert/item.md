---
title: 'Developer Level coreBOS Certification Program'
metadata:
    description: 'Developer Level coreBOS Certification Program'
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
        - course
    tag:
        - certification
---

-   Basic programming guidelines (Code Complete, Nextcloud)
     -   help your future self!!
         -   name consistently: help yourself understand
         -   commit consistently: help yourself remember
         -   sign your work: be proud of your mistakes: they teach you
         -   learn: constantly: help yourself be smarter and more productive
-   Instalación. Programas involucrados. Herramientas
     -   Apache, Mysql, PHP, Javascript
     -   phpmyadmin, IDE, git
     -   firefox/chrome
     -   meldmerge
     -   phpmd, phpcs, phpcbf, phpdoctor
     -   phpunit
     -   coreBOS Programming and committing guidelines
-   I+C Devel Environment course
-   Estructura física: donde esta el código
     -   escribible
         -   cache, logs, Smarty/templates_c, test
         -   storage
         -   user_privileges
     -   base datos
         -   adodb
         -   schema, install
     -   programa
         -   data
         -   Image
         -   include
             -   js
             -   utils
             -   Webservice
         -   jscalendar
         -   log4php
         -   modules
             -   languages
         -   Smarty
             -   templates
         -   themes
         -   user_privileges
     -   cron
-   Ejecución acciones. Como se llaman los scripts.
     -   Desglosando config.inc.php
     -   Desglosando index.php
-   Estructura Base de datos: donde están los datos
     -   Nombre tablas y sus relaciones
     -   Como buscar y encontrar lo que necesitas
     -   Copias: mysqldump
-   Scripts y Templates importantes
     -   include/utils
         -   DetailView*
         -   EditView*
         -   ListView*
         -   Related
     -   smarty/templates/
-   Como modificar una plantilla
-   Estructura módulo
     -   Ficheros y relaciones. Base de datos
     -   Ficheros de idiomas
-   Programando: vtlib
     -   Como crear nuevo modulo
     -   Como modificar módulos existentes
     -   Events y Hooks
-   Desarrollando un modulo
-   Depurando problemas
     -   Logging: log4php: $log→fatal()
     -   Smarty/libs/Smarty.class.php
-   Extendiendo: workflow, event handler y service crons/crons
-   coreBOS Updater how to keep your coreBOS up to date
-   Introduccion a Webservice
-   Security. oWASP
-   Recomendaciones y consejos
     -   Source code control: GIT
     -   Copias