---
title: dimensionLine resource type | Microsoft Docs
description: A dimension line in Dynamics 365 for Financials.
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

# dimensionLine resource type
Represents a dimension line in Dynamics 365 for Financials.

## Methods

| Method                                                         | Return Type  |Description                 |
|:---------------------------------------------------------------|:-------------|:---------------------------|
|[GET Dimension Line](../api/dynamics_get_dimensionline.md)      |Dimension Line|Get Dimension Line object   |
|[POST Dimension Line](../api/dynamics_create_dimensionline.md)  |Dimension Line|Create Dimension Line object|
|[PATCH Dimension Line](../api/dynamics_update_dimensionline.md) |Dimension Line|Update Dimension Line object|
|[DELETE Dimension Line](../api/dynamics_delete_dimensionline.md)|none          |Delete Dimension Line object|

## Properties
| Property	     | Type	                 |Description                                               |
|:---------------|:----------------------|:---------------------------------------------------------|
|parentId        |GUID                   |The ID of the parent entity. Non editable.                |
|id              |GUID                   |The unique ID of the dimension line. Non editable.        |
|code            |string, maximum size 20| The code of the dimension.                               |
|displayName     |string, maximum size 30| The display name of the dimension. Read-Only.            |
|valueId         |GUID                   |The unique ID of the value of the dimension.              |
|valueCode       |string, maximum size 20|The code of the value of the dimension.                   |
|valueDisplayName|string, maximum size 50|The display name of the value of the dimension. Read-Only.|

## Relationships
A dimension line must have a "Parent Entity" with an Id, that is represented by the parent Id.
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

## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 
