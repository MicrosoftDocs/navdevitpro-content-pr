---
title: Item Categories resource type | Microsoft Docs
description: An itemCategory.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/08/2017
ms.author: solsen
---

# itemCategory resource type

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|Get itemCategories|itemCategories|Get a itemCategories object.|
|Create itemCategories|itemCategories|Create a itemCategories object.|
|Update itemCategories|itemCategories|Update a itemCategories object.|
|Delete itemCategories|none|Delete a itemCategories object.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the itemCategory. Read-Only.|
|code|string|The itemCategory code.|
|displayName|string|The itemCategories display name.|
|lastModifiedDateTime|datetime|The last datetime the itemCategory was modified. Read-Only.|  


## Relationships
None

## JSON representation

Here is a JSON representation of the itemCategories.


```
{
  "id": "GUID",
  "code": "string",
  "displayName": "string",
  "lastModifiedDateTime": "datetime"
}
```

## See Also
[Graph Reference](graph-reference.md)  