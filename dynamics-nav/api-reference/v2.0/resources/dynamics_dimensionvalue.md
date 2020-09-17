---
title: dimensionValue resource type | Microsoft Docs
description: A dimension value object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/17/2020
ms.author: solsen
---

# dimensionValue resource type
Represents an dimension value in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods
| Method | Return Type|Description |
|:--------------------|:-----------|:-------------------------|
|[GET dimensionValue](../api/dynamics_dimensionValue_Get.md)|dimensionValue|Gets a dimension value object.|






## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|id|GUID|The unique ID of the item. Non-editable.|
|code|string|The code of the dimension value.|
|displayName|string|Specifies the dimension value's name. This name will appear on all sales documents for the dimension value.|
|lastModifiedDateTime|datetime|The last datetime the dimension value was modified. Read-Only.|


## JSON representation

Here is a JSON representation of the dimensionValue resource.


```json
{
   "id": "GUID",
   "code": "string",
   "displayName": "string",
   "lastModifiedDateTime": "datetime"
}
```
## See also

[GET dimensionValue](../api/dynamics_dimensionValue_Get.md)

