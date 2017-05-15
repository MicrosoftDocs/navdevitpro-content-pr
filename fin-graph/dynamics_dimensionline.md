---
title: dimensionLine resource type | Microsoft Docs
description: A dimension line.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/02/2017
ms.author: solsen
---

# dimensionLine resource type
Represents a dimensionLine resource type in [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET Dimension Line](dynamics_get_dimensionline.md)|Dimension Line|Get Dimension Line object|
|[POST Dimension Line](dynamics_create_dimensionline.md)|Dimension Line|Create Dimension Line object|
|[PATCH Dimension Line](dynamics_update_dimensionline.md)|Dimension Line|Update Dimension Line object|
|[DELETE Dimension Line](dynamics_delete_dimensionline.md)|none|Delete Dimension Line object|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|parentId|GUID|The ID of the parent entity. Read-Only.|
|id|GUID|The unique ID of the dimension line. Read-Only.|
|code|string, maximum size 20| The code of the dimension.|
|displayName|string, maximum size 30| The display name of the dimension. Read-Only.|
|valueId|GUID|The unique ID of the value of the dimension.|
|valueCode|string, maximum size 20|The code of the value of the dimension.|
|valueDisplayName|string, maximum size 50|The display name of the value of the dimension. Read-Only.|

## Relationships
A "Parent Entity" (parentId) must exist in the related endpoint.
"Parent Entity" can be one of the following:
 1) Journal Line
 2) Customer Payment.

A Dimension (id) must exist in the Dimensions endpoint.

A Dimension Value (valueId) must exist in the Dimension Values endpoint.

## JSON representation

Here is a JSON representation of the resource.

```json
{
  "parentId": "GUID",
  "id": "GUID",
  "code": "String",
  "displayName": "String",
  "valueId": "GUID",
  "valueCode": "String",
  "valueDisplayName": "String"
}

```

## See Also
[Graph Reference](dynamics_graph_reference.md)  
