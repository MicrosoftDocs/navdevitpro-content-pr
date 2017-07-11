---
title: Tax Group resource type | Microsoft Docs
description: A Tax Group.
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

# Tax group resource type
Represents a taxGroups resource type in Dynamics 365 for Financials.


## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET taxGroup](../api/dynamics_get_taxGroups.md)|taxGroup|Get a Tax Group.|
|[POST taxGroup](../api/dynamics_create_taxGroups.md)|taxGroup|Create a Tax Group.|
|[PATCH taxGroup](../api/dynamics_update_taxGroups.md)|taxGroup|Update a Tax Group.|
|[DELETE taxGroup](../api/dynamics_delete_taxGroups.md)|none|Delete a Tax Group.|

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
[Working with Dynamics 365 for Financials in Microsoft Graph](../api/dynamics_graph_reference.md)  
