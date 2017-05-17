---
title: dimension resource type | Microsoft Docs
description: A dimension.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ems.date: 02/08/2017
ms.author: solsen
---

# Dimension resource type
Represents a dimension resource type in Dynamics 365 for Financials.

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET dimension](../api/dynamics_get_dimension.md)|dimension|Get a dimension.|


## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the item.|
|code|string, maximum size 20|The dimension code.|
|displayName|string|Specifies the dimension's name. This name will appear where the dimension is used.|
|lastModifiedDateTime|datetime|The last datetime the dimension was modified.|  


## JSON representation

Here is a JSON representation of the resource.


```json
{

    "id": "GUID",
    "code": "string",
    "displayName": "string",
    "lastModifiedDateTime": "datetime"
}
```


## See also
[Graph Reference](../api/dynamics_graph_reference.md)  
