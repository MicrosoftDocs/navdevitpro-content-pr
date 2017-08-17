---
title: companies resource type | Microsoft Docs
description: A Company.
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

# company resource type
Represents a companies resource type in Dynamics 365 for Financials.


## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET company](../api/dynamics_get_companies.md)|company|Get a company.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the company. Read-Only.|
|name|string|Specifies the company.|
|displayName|string|Specifies the company display name.|


## Relationships
None

## JSON representation

Here is a JSON representation of the company.

```json
{
  "id": "GUID",
  "name": "string",
  "displayName": "string"
}

```

## See Also
[Working with Dynamics 365 for Financials in Microsoft Graph](../api/dynamics_graph_reference.md)  
