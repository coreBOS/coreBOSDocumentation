---
title: 'Administrator/Implementor Level coreBOS Certification Program'
metadata:
    description: 'Implementor Level coreBOS Certification Program'
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
        - adminmanual
    tag:
        - certification
---

## Administrator/Implementor Level coreBOS Certification Program

-   Analysis and Design of the new coreBOS system
-   Installation in Windows and Linux
    -   GIT for implementors
-   Overview of all modules and fields: what is already there
-   Administración usuarios y permisos
-   Herramientas Administración del Sistema
    -   Numeración factura/documentos
    -   Servidor correo saliente
    -   Tipos de Impuesto
-   Personalizacion de módulos, campos y listas
-   Traducciones
-   Importación/Exportacion información
-   Configuration tools
    -   Configuración empresa: mono empresa, unica linea de numeración de facturas
    -   Menu Editor
    -   Ayudas en línea
    -   Global Variables
    -   Business Actions
    -   Business Maps
    -   Auditoria
-   Flujos de Trabajo. Notificaciones
-   Plantillas EMail y Documentos (GenDoc)
-   Administración de Inventario
-   Modulos y Extensiones
-   Copias de seguridad
    -   directorios importantes
-   Best Practices
    -   Step by Step instructions to set up a coreBOS
    -   Teaching your users
        -   see Como empezar y añadir "tus procesos"

### Analysis and Design of the new coreBOS system

-   coreBOS Requirements Worksheet
-   Analisis de Procesos
    -   Estudiar procesos de negocio afectados
    -   Paso a paso, poco a poco
    -   Measure, review, improve
-   Instalación
    -   Instalar siguiendo instrucciones
    -   Crear Usuario admininistrador
    -   Inst Idioma
        -   edit config.inc.php: default language es_ES
-   Administrar
    -   Info Empresa: poner logo
    -   Email Servidor Saliente
    -   Sistema (moneda predeterminada entre otros)
        -   Monedas (si procede)
        -   crontab planificador
     ```
     */4 * * * * root cd full_path_to_corebos/cron; ./vtigercron.sh
     ```
    -   Crear roles y usuarios
     -   Privilegios
         -   Few users in the enterprise have few requirements to privilege administration
         -   Based on:
             -   Who can see data?
             -   Who can change data?
             -   Who can delete data?
             -   Who can create data?
         -   Number users
             -   single: no need for privileges
             -   small: prohibir acceso a información confidencial y personal mediante perfiles básicos
             -   many: perfiles y grupos asociados con cada puesto de trabajo
        -   Niveles de Acceso
         -   1.- Perfiles (seguridad)
         -   2.- Roles
         -   3.- Usuarios (privilegios asociados por rol)
         -   Grupos
        -   Informar a usuarios de como entrar y configurar sus datos de correo
-   Minor cosmetics and UI Changes
    -   Definir distribución y visibilidad de las pestañas
    -   Methodically go through all the modules and examine all the terminology, and field names and drop-down lists to identify all the changes.
    -   Change names of modules, values of dropdownlists, add and remove fields, rearrange layouts
-   Importar datos
    -   Export info from aplicación actual
    -   Importar Cuentas/Empresas primero
    -   Importar Contactos
-   Customizations
    -   Minor cosmetics
    -   Minor UI changes
    -   Major Application changes: Modulos adicionales y enlace con servicios CMS
    -   Application Integration
-   Informes
-   Terminales cliente
    -   Chrome recommended
    -   Thunderbird Extension
    -   Outlook (solo para aquellos que lo estén utilizando ya)
-   Testing
-   Formación: familiarización y soltura en uso de la aplicación. Crear entusiasmo.

### coreBOS Requirements Worksheet

-   CRM Orientation
 -  Sales oriented
 -  Support oriented
 -  Order management oriented
-   Procesos
 -  Modulos
    -   Agenda
    -   Oportunidades
    -   Precontactos
    -   Cuentas/Contactos
    -   Campaña
    -   Producto
    -   Tarifas
    -   Proveedor
    -   Presupuesto
    -   Orden de Compra
    -   Orden de Venta
    -   Factura
    -   Incidencias
    -   FAQ
-   Requerimientos adicionales
 -  Modulos
 -   Procesos
-   Personalización
 -  Establecer idiomas soportados
 -  Niveles de Acceso
    -   Organizaciones
    -   Perfiles (seguridad)
    -   Roles
    -   Grupos
    -   Usuarios: nom, apellido, email, perfil
-   Personalizar modulos
 -  Cuales aparecen y cuales no
 -  Campos personalizables
 -  Listas
 -   Info Empresa
    -   poner logo en login y app
    -   personalizar documentos
-   Cuentas de correo
-   Importar datos. Crear Cuentas Primero (Entidades)
-   Informes
-   Equipo donde se instalará
-   Copias de Seguridad
-   Terminales cliente
    -   Instalar Chrome
    -   Thunderbird Extension
    -   Outlook (solo para aquellos que lo estén utilizando ya)