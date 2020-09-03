---
title: taxGroup resource type | Microsoft Docs
description: An tax group object in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# taxGroup resource type
Represents an tax group object in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET taxGroups](../api/dynamics_taxGroups_get.md)|taxGroups|Gets a tax group object.|
|[POST taxGroups](../api/dynamics_create_taxGroups.md)|taxGroups|Creates a tax group object.|
|[PATCH taxGroups](../api/dynamics_taxGroups_update.md)|taxGroups|Updates a tax group object.|
|[DELETE taxGroups](../api/dynamics_taxGroups_delete.md)|none|Deletes a tax group object.|

## Properties

| Property     | Type   |Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the taxGroup. Read-Only.|
|code|string|Specifies the tax group.|
|displayName|string|Specifies the tax group display name.|
|lastModifiedDateTime|datetime|The last datetime the tax group was modified. Read-Only.|  


## JSON representation

Here is a JSON representation of the resource.


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
  
[Get Tax Groups](../api/dynamics_taxgroups_get.md)  
[Create Tax Groups](../api/dynamics_create_taxgroups.md)  
[Update Tax Groups](../api/dynamics_taxgroups_update.md)  
