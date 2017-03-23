---
title: Item Categories resource type | Microsoft Docs
description: An Item Categories.
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

# Item Categories resource type
Represents an itemCategories resource type in [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET itemCategories](get-itemcategories.md)|itemCategories|Get an Item Category.|
|[POST itemCategories](create-itemcategories.md)|itemCategories|Create an Item Category.|
|[PATCH itemCategories](update-itemcategories.md)|itemCategories|Update an Item Category.|
|[DELETE itemCategories](delete-itemcategories.md)|none|Delete an Item Category.|

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

```json
{
  "id": "GUID",
  "code": "string",
  "displayName": "string",
  "lastModifiedDateTime": "datetime"
}
```

## See Also
[Graph Reference](graph-reference.md)  
