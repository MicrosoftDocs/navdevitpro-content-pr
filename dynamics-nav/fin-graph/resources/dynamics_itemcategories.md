---
title: itemCategories resource type | Microsoft Docs
description: An item category in Dynamics 365 for Financials.
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

# itemCategories resource type
Represents a category for a number of items in Dynamics 365 for Financials.

## Methods

| Method                                                          | Return Type  |Description             |
|:----------------------------------------------------------------|:-------------|:-----------------------|
|[GET itemCategories](../api/dynamics_itemcategories_get.md)      |itemCategories|Get an item category.   |
|[POST itemCategories](../api/dynamics_create_itemcategories.md)  |itemCategories|Create an item category.|
|[PATCH itemCategories](../api/dynamics_itemcategories_update.md) |itemCategories|Update an item category.|
|[DELETE itemCategories](../api/dynamics_itemcategories_delete.md)|none          |Delete an item category.|

## Properties
| Property	         | Type	  |Description                                     |
|:-------------------|:-------|:-----------------------------------------------|
|id                  |GUID    |The unique ID of the itemCategory. Non-editable.|
|code                |string  |The itemCategory code.                          |
|displayName         |string  |The itemCategories display name.                |
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

## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 
