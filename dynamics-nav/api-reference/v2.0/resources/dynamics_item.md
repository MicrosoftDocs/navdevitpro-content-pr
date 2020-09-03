---
title: item resource type | Microsoft Docs
description: An item object in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# item resource type
Represents an item in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method                                      |Return Type|Description |
|:--------------------------------------------|:----------|:-----------|
|[GET item](../api/dynamics_item_get.md)      |item      |Gets an item object.   |
|[POST item](../api/dynamics_create_item.md)  |item      |Creates an item object.|
|[PATCH item](../api/dynamics_item_update.md) |item      |Updates an item object.|
|[DELETE item](../api/dynamics_item_delete.md)|none       |Deletes an item object.|

## Navigation

| Navigation |Return Type| Description |
|:----------|:----------|:-----------------|
|[itemCategory](../resources/dynamics_itemcategory.md)|itemCategory   |Gets the itemcategory of the item.|
|[unitOfMeasure](../resources/dynamics_unitofmeasure.md)|unitOfMeasure   |Gets the unitofmeasure of the item.|
|[picture](../resources/dynamics_picture.md)|picture   |Gets the picture of the item.|
|[defaultDimensions](../resources/dynamics_defaultdimensions.md)|defaultDimensions   |Gets the defaultdimensions of the item.|
|[itemVariants](../resources/dynamics_itemvariants.md)|itemVariants   |Gets the itemvariants of the item.|

## Properties

| Property           | Type |Description                                          |
|:-------------------|:-------|:----------------------------------------------------|
|id                  |GUID    |The unique ID of the item. Non-editable.             |
|number              |string  |The item number.                                     |
|displayName         |string  |Specifies a description of the item.                 |
|type                |string  |The inventory type for the item; Inventory, Service, and Non-Inventory. This is a required property.|
|blocked             |boolean |Specifies that transactions with the item cannot be posted, for example, because the item is in quarantine. Set to **true**, if item is blocked.|
|baseUnitOfMeasureId |GUID    |Specifies the ID of the unit of measure.             |
|baseUnitOfMeasure   |[NAV.UnitOfMeasure](../resources/dynamics_complextypes.md)|Specifies the unit in which the item is held in inventory.|
|gtin                |numeric |This is the Global Trade Item Number.                |
|itemCategory        |[NAV.ItemCategory](../resources/dynamics_complextypes.md)|Specifies the category that the item belongs to.|
|inventory           |decimal |Specifies how many units, such as pieces, boxes, or cans, of the item are in inventory. Read-Only.|
|unitPrice           |decimal |Specifies the price for one unit of the item in the specified currency.|
|priceIncludesTax    |boolean |Specifies that the unitPrice includes tax. Set to **true**, if unitPrice includes tax.|
|unitCost            |decimal |Specifies the cost per unit of the item.             |
|taxGroupId          |GUID    |Specifies the ID of the Tax Group for the item.      |
|taxGroupCode        |numeric |A Tax Group represents a group of inventory item or resources that are subject to identical tax terms.|
|lastModifiedDateTime|datetime|The last datetime the item was modified. Read-Only.  |  


## JSON representation

Here is a JSON representation of the resource.


```json
{
   "id": "GUID",
   "number": "string",
   "displayName": "string",
   "type": "NAV.contactType",
   "itemCategoryId": "GUID",
   "itemCategoryCode": "string",
   "blocked": "boolean",
   "gtin": "string",
   "inventory": "decimal",
   "unitPrice": "decimal",
   "priceIncludesTax": "boolean",
   "unitCost": "decimal",
   "taxGroupId": "GUID",
   "taxGroupCode": "string",
   "baseUnitOfMeasureId": "GUID",
   "baseUnitOfMeasureCode": "string",
   "lastModifiedDateTime": "datetime"
}
```

## See also



[Error Codes](../dynamics_error_codes.md)  
[Item](../resources/dynamics_item.md)  
[Get Item](../api/dynamics_item_get.md)  
[Post Item](../api/dynamics_create_item.md)  
[Patch Item](../api/dynamics_item_update.md)  
[Delete Item](../api/dynamics_item_delete.md)  