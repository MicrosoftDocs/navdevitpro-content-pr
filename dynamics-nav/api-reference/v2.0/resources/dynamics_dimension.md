---
title: dimension resource type | Microsoft Docs
description: A dimension object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/15/2020
ms.author: solsen
---

# dimension resource type
Represents an dimension in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method              | Return Type|Description               |
|:--------------------|:-----------|:-------------------------|
|[GET dimension](../api/dynamics_dimension_Get.md)|dimension|Gets a dimension object.|
|[DELETE dimension](../api/dynamics_dimension_Delete.md)|dimension|Deletes a dimension object.|
|[POST dimension](../api/dynamics_dimension_Create.md)|dimension|Creates a dimension object.|
|[PATCH dimension](../api/dynamics_dimension_Update.md)|dimension|Updates a dimension object.|




## Navigation

| Navigation |Return Type| Description |    
|:----------|:----------|:-----------------|
|[dimensionValues](../resources/dynamics_dimensionvalues.md)|dimensionValues |Gets the dimensionvalues of the dimension.|


## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|id|GUID|The unique ID of the item. Non-editable.|
|code|string|The code of the dimension.|
|displayName|string|Specifies the dimension's name. This name will appear on all sales documents for the dimension.|
|lastModifiedDateTime|datetime|The last datetime the dimension was modified. Read-Only.|


## JSON representation

Here is a JSON representation of the dimension resource.


```json
{
   "id": "GUID",
   "code": "string",
   "displayName": "string",
   "lastModifiedDateTime": "datetime"
}
```
## See also

[GET dimension](../api/dynamics_dimension_Get.md)
[DELETE dimension](../api/dynamics_dimension_Delete.md)
[POST dimension](../api/dynamics_dimension_Create.md)
[PATCH dimension](../api/dynamics_dimension_Update.md)

