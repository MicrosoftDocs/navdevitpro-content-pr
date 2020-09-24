---
title: defaultDimension resource type | Microsoft Docs
description: A default dimension object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/01/2020
ms.author: solsen
---

# defaultDimension resource type
Represents a default dimension in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods
| Method | Return Type|Description |
|:--------------------|:-----------|:-------------------------|
|[GET defaultDimension](../api/dynamics_defaultDimension_Get.md)|defaultDimension|Gets a default dimension object.|
|[DELETE defaultDimension](../api/dynamics_defaultDimension_Delete.md)|none|Deletes a default dimension object.|
|[POST defaultDimension](../api/dynamics_defaultDimension_Create.md)|defaultDimension|Creates a default dimension object.|
|[PATCH defaultDimension](../api/dynamics_defaultDimension_Update.md)|defaultDimension|Updates a default dimension object.|




## Navigation

| Navigation |Return Type| Description |    
|:----------|:----------|:-----------------|
|[item](../resources/dynamics_item.md)|item |Gets the item of the defaultDimension.|
|[account](../resources/dynamics_account.md)|account |Gets the account of the defaultDimension.|
|[dimension](../resources/dynamics_dimension.md)|dimension |Gets the dimension of the defaultDimension.|
|[dimensionValue](../resources/dynamics_dimensionvalue.md)|dimensionValue |Gets the dimensionvalue of the defaultDimension.|
|[customer](../resources/dynamics_customer.md)|customer |Gets the customer of the defaultDimension.|
|[vendor](../resources/dynamics_vendor.md)|vendor |Gets the vendor of the defaultDimension.|
|[employee](../resources/dynamics_employee.md)|employee |Gets the employee of the defaultDimension.|


## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|id|GUID|The unique ID of the item. Non-editable.|
|parentType|NAV.defaultDimensionParentType|The type of the parent document of the default dimension. It can be " ", "Customer", "Item", "Vendor" or "Employee".|
|parentId|GUID|The ID of the parent entity. |
|dimensionId|GUID|The unique ID of dimension.|
|dimensionCode|string|The dimension code.|
|dimensionValueId|GUID|The unique ID of the dimension value.|
|dimensionValueCode|string|The dimension value code.  |
|postingValidation|string|Specifies how default dimensions and their values must be used.|


## JSON representation

Here is a JSON representation of the defaultDimension resource.


```json
{
   "id": "GUID",
   "parentType": "NAV.defaultDimensionParentType",
   "parentId": "GUID",
   "dimensionId": "GUID",
   "dimensionCode": "string",
   "dimensionValueId": "GUID",
   "dimensionValueCode": "string",
   "postingValidation": "string"
}
```
## See also

[GET defaultDimension](../api/dynamics_defaultDimension_Get.md)
[DELETE defaultDimension](../api/dynamics_defaultDimension_Delete.md)
[POST defaultDimension](../api/dynamics_defaultDimension_Create.md)
[PATCH defaultDimension](../api/dynamics_defaultDimension_Update.md)

