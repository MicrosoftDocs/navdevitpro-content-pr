---
title: tax area resource type | Microsoft Docs
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

# Tax area resource type
Represents a tax area resource type in Dynamics 365 for Financials.

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET tax area](../api/dynamics_get_taxarea.md)|tax area|Get Tax Area.|
|[POST tax area](../api/dynamics_create_taxarea.md)|tax area|Create Tax Area.|
|[PATCH tax area](../api/dynamics_update_taxarea.md)|tax area|Update Tax Area.|
|[DELETE tax area](../api/dynamics_delete_taxarea.md)|none|Delete Tax Area.|

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
