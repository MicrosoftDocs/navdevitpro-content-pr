---
title: taxAreas resource type | Microsoft Docs
description: A tax area.
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

# taxAreas resource type
Represents a tax area resource type in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../includes/navnow_md.md)] see [Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md).

## Methods
| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET taxAreas](../api/dynamics_taxarea_get.md)|taxAreas|Gets a tax area object.|
|[POST taxAreas](../api/dynamics_create_taxarea.md)|taxAreas|Creates a tax area object.|
|[PATCH taxAreas](../api/dynamics_taxarea_update.md)|taxAreas|Updates a tax area object.|
|[DELETE taxAreas](../api/dynamics_taxarea_delete.md)|none|Deletes a tax area object.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the tax area. Non-editable.|
|code|string, maximum size 20| The code of the tax area.|
|displayName|string, maximum size 50| The display name of the tax area.|
|lastModifiedDateTime|datetime|The last datetime the tax area was modified. Read-Only.|

## Relationships

## JSON representation

Here is a JSON representation of the resource.


```json
{
  "id": "GUID",
  "code": "String",
  "displayName": "String",
  "lastModifiedDateTime": "datetime"
}
```

## See also
[Graph Reference](../api/dynamics_graph_reference.md)  
