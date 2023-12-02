---
title: 'Multi Warehouse Enhancements'
metadata:
    description: 'Perspective of three modules to manage multiwarehouse stock and movements of material between warehouses.'
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

Perspective of three (or four) modules to manage multiwarehouse stock and movements of material between warehouses.

===

![multi warehouse design](multialmacen.png)

- Warehouse. New module with all data of a warehouse. Related in +info with a 1:m relation to Stock and Movements
- Stock. New module with, warehouse capture, product capture and stock numeric field. In this module, we can easily filter or report on the stock of given products or families, or warehouse,...
- Movements. New module with, source warehouse capture, destination warehouse capture, product capture and numeric field that indicates the amount of product moved from source to destination. Records in this module must increase or decrease the corresponding stock records.
- Product. Existing module. Related in +info with a 1:m relation to Stock and Movements
- Once created the infrastructure, the application must be modified to control warehouse selection and stock. We can take two approaches:
    - Multiwarehouse on each invoice (Q/SO/PO)
      - product capture must now contemplate the warehouse it is coming from and permit not only searching by warehouse but also consulting the available stock in each warehouse
      - the warehouse information must be captured and saved on each product line
      - adapt current increase and decrease stock functions to the new structure, by creating the corresponding movement records
      - convert the current stock field in products to readonly and update it consistently through the stock module
    - One warehouse on each invoice (Q/SO/PO) **THIS ONE HAS BEEN IMPLEMENTED**
      - add one warehouse capture field on Q/SO/PO/I, this will be the warehouse the whole invoice will work with, all the products on the invoice will be from this warehouse
      - modify the Q &gt; SO &gt; I conversion to pass along the warehouse field
      - modify product line popup to automatically show only products from the selected warehouse
      - adapt current increase and decrease stock functions to new structure, by creating the corresponding movement records
      - convert the current stock field in products to readonly and update it consistently through the stock module
- Review and validate reporting to make sure we can get information about all the new modules and stock movements:

![](/wiki/stockmovements.png)

The original design
-------------------

<img src="multialmacen.jpg" width="60%" alt="multi warehouse design" />

How to use
----------

You have two virtual warehouse, Sales and Purchase. These warehouses simulate the stock movement when you do a purchase or sale.

To work correctly, you have to create your physical warehouse to do the purchase stock movement to your warehouse or when you do a sale from your physical warehouse.

You can do these movements using the virtual warehouse, for example:

### Movements

- When you want to do a purchase for your warehouse, you have to go to Inventory -&gt; Stock Movement and create a new movement.

![](img1.png?width=100%)

- There, you have to select the source warehouse, that in this case is Purchase, select destination warehouse, for example, WH00001 and finally select the product and units that you have bought.
- And if you want to do a sale from your warehouse WH00001, you have to select the source warehouse, WH00001, and then the Sales warehouse as the destination.
- If you have more warehouses, you can do movements between them selecting the source and destination warehouse accordingly

### Massive Movements

To make the creation of movements easier we have added a [Massive Movements module](https://github.com/coreBOS/MassiveMovements). This module will permit you to quickly move many products between warehouses by creating records.

### Workflows:

We have created three workflows to help control the stock when working with PO and Invoice (SO). The first two are related to the normal work sequence in coreBOS while the third is to handle returns.

As normal, to configure workflows you have to go to Settings-&gt;Workflows, where we have already added the new workflows related to the entities, so you just have to configure them depending on your business model conditions.

![](img2.png?width=100%)

#### Decrement Stock

This is when you make a sale through an Invoice or Sales Order. You have to edit the first workflow (module -&gt; Invoice , description -&gt; UpdateInventoryProducts On Every Save), then edit the Task and change the UpdateInventory function to mwDecrementStock.

![](img3.png?width=100%)

#### Increment Stock

This is when you buy products on a Purchase Order. You have to create a new workflow with the Purchase Order module and create a new task selecting Invoke Custom Function. In this task, you have to select the mwIncrementStock.

![](img4.png?width=100%)

#### Return Stock

You return stock when you cancel an Invoice (Sales Order) or return products to your vendor. Normally you would create new workflows with a condition depending on some status field on the record. The mwReturnStock custom function knows when it is returning a Sale or a Purchase so we use the same custom function for both.

### Notes:

 + Stock module, you only have to use for reports, filters, etc, .... you don't have to create new stock here, because this action is done automatically by the Stock Movement module. You can easily disable the create/edit option in the profiles settings.

![](img5.png?width=100%)  
![](img6.png?width=100%)

How to import Products and initialize stock.
--------------------------------------------

If we have products to import and we want to initialize the stock, we have to follow the next steps.

- First we have to import a CSV with products to the Products module.
- Now we have all our products imported and we want to initialize the stock and first movement from the virtual Purchase warehouse to our warehouse.
- If you have created a new warehouse, you can export the products that you need to initialize from the Products Module. We need the CSV that coreBOS generates to obtain the product number in the application. Something like this: `Products::::PRO27`

* Now we can edit this CSV and add or delete columns we need to import Movements to coreBOS. We have to obtain a CSV like this:

<img src="movements_example.png" class="align-center" width="100%" />

- After importing these movements we can see that we have new stock registers.

### Questions and Answers:

**En las pestañas de movimientos y stock, ayudaría muchísimo si pudieramos saber de qué IN, SO o PO se está haciendo el movimiento, hoy es difícil rastrear este movimiento.**

Stock es el número de unidades totales de un producto en un almacén, es el resultado de TODOS los movimientos realizados, por tanto no tiene sentido tener una factura o compra asociada.

El movimiento, en cambio, es EXACTAMENTE el cambio de unidades de stock entre dos almacenes como resultado de una venta o compra, por tanto en el mismo movimiento tienes un enlace a la entidad que ha generado el movimiento e incluso el número de línea en el mismo. Deberías poder ir a la vista detalle de cualquier movimiento y verás el registro que lo ha generado.

Para poder ver todos los movimientos que representan el stock actual deberías poder hacer un informe o filtro en un almacén y un producto. Esos movimientos son los que representan el stock actual en el almacén.

<hr>
<br>

**The concept/menu item "stock", I’m afraid that I don’t know how/why it's used?**

As can be read above, the stock module is to make reporting and filtering on stock easy. It is automatically filled in when a movement is created. The movement will automatically create/update the stock records in the stock module, so there is no need to do anything there. It is just for reporting. We could have saved that information internally and then invented some way for you to filter and report on the stock but we figured that adding the information to a normal module would consume the same database space (more or less) and we wouldn't have to invent anything, all users would already know how to report and filter on the information there.
