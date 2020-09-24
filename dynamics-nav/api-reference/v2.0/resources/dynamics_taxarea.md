---
title: taxArea resource type | Microsoft Docs
description: A tax area object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/01/2020
ms.author: solsen
---

# taxArea resource type
Represents a tax area in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods
| Method | Return Type|Description |
|:--------------------|:-----------|:-------------------------|
|[GET taxArea](../api/dynamics_taxArea_Get.md)|taxArea|Gets a tax area object.|
|[DELETE taxArea](../api/dynamics_taxArea_Delete.md)|none|Deletes a tax area object.|
|[POST taxArea](../api/dynamics_taxArea_Create.md)|taxArea|Creates a tax area object.|
|[PATCH taxArea](../api/dynamics_taxArea_Update.md)|taxArea|Updates a tax area object.|






## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|id|GUID|The unique ID of the item. Non-editable.|
|code|string|The code of the tax area.|
|displayName|string|Specifies the tax area's name. This name will appear on all sales documents for the tax area.|
|taxType|NAV.taxBufferType|Specifies the type of tax. It can be "Sales Tax" or "VAT".|
|lastModifiedDateTime|datetime|The last datetime the tax area was modified. Read-Only.|


## JSON representation

Here is a JSON representation of the taxArea resource.


```json
{
   "id": "GUID",
   "code": "string",
   "displayName": "string",
   "taxType": "NAV.taxBufferType",
   "lastModifiedDateTime": "datetime"
}
```
## See also

[GET taxArea](../api/dynamics_taxArea_Get.md)   
[DELETE taxArea](../api/dynamics_taxArea_Delete.md)   
[POST taxArea](../api/dynamics_taxArea_Create.md)   
[PATCH taxArea](../api/dynamics_taxArea_Update.md)   

