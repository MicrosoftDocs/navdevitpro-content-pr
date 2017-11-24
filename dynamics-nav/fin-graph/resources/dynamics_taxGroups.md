---
title: taxGroups resource type | Microsoft Docs
description: A tax group object in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)]. 
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/11/2017
ms.author: solsen
---

# taxGroups resource type
Represents a taxGroups resource type in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../includes/navnow_md.md)] see [Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md).

## Methods
| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET taxGroups](../api/dynamics_taxGroups_get.md)|taxGroups|Gets a tax group object.|
|[POST taxGroups](../api/dynamics_create_taxGroups.md)|taxGroups|Creates a tax group object.|
|[PATCH taxGroups](../api/dynamics_taxGroups_update.md)|taxGroups|Updates a tax group object.|
|[DELETE taxGroups](../api/dynamics_taxGroups_delete.md)|none|Deletes a tax group object.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the taxGroup. Read-Only.|
|code|string|Specifies the tax group.|
|displayName|string|Specifies the tax group display name.|
|lastModifiedDateTime|datetime|The last datetime the tax group was modified. Read-Only.|  


## Relationships
None

## JSON representation

Here is a JSON representation of the taxGroup.

```json
{
  "id": "GUID",
  "code": "string",
  "displayName": "string",
  "lastModifiedDateTime": "datetime"
}

```

## See Also
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../api/dynamics_graph_reference.md)  
