---
title: item resource type | Microsoft Docs
description: An item.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/08/2017
ms.author: solsen
---

# Item resource type
Represents an item resource type in [!INCLUDE[d365fin_long_md](../includes/d365fin_long_md.md)].

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET item](../api/dynamics_get_item.md)|item|Get item.|
|[POST item](../api/dynamics_create_item.md)|item|Create item.|
|[PATCH item](../api/dynamics_update_item.md)|item|Update item.|
|[DELETE item](../api/dynamics_delete_item.md)|none|Delete item.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the item. Read-Only.|
|number|string|The item number.|
|displayName|string|Specifies a description of the item.|
|type|numeric|The inventory type for the item. 1 = inventory item, 2 = service item. This is a required property.|
|blocked|boolean|Specifies that transactions with the item cannot be posted, for example, because the item is in quarantine. Set to **True** if item is blocked.|
|baseUnitOfMeasure|[NAV.UnitOfMeasure](../api/dynamics_complex_types.md)|Specifies the unit in which the item is held in inventory.|
|gtin|numeric|This is the Global Trade Item Number.|
|itemCategoryCode|[NAV.ItemCategory](../api/dynamics_complex_types.md)|Specifies the category that the item belongs to. Item categories also contain any assigned item attributes.|
|inventory|decimal|Specifies how many units, such as pieces, boxes, or cans, of the item are in inventory. Read-Only.|
|unitPrice|decimal|Specifies the price for one unit of the item in the specified currency.|
|priceIncludesTax|boolean|Specifies that the unitPrice includes tax. Set to **True** if unitPrice includes tax.|
|unitCost|decimal|Specifies the cost per unit of the item.|
|taxGroupCode|numeric|A Tax Group represents a group of inventory items or resources that are subject to identical tax terms.|
|lastModifiedDateTime|datetime|The last datetime the item was modified. Read-Only.|  


## Relationships
A Tax Group(taxGroupCode) must exist in the Tax Group table.

## JSON representation

Here is a JSON representation of the resource.


```json
{
      "id": "GUID",
      "number": "string",
      "displayName": "string",
      "type": "string",
      "blocked": "boolean",
      "baseUnitOfMeasure": "NAV.UnitOfMeasure",
      "gtin": "numeric",
      "itemCategory": "NAV.ItemCategory",
      "inventory": "decimal",
      "unitPrice": "decimal",
      "priceIncludesTax": "boolean",
      "unitCost": "decimal",
      "taxGroupCode": "string",
      "lastModifiedDateTime": "datetime"
}

```

## See also
[Graph Reference](../api/dynamics_graph_reference.md)  
