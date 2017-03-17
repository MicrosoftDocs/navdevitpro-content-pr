---
title: shipmentMethod resource type | Microsoft Docs
description: A shipmentMethod.
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

# shipmentMethod resource type

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|Get shipmentMethod|shipmentMethod|Get a shipmentMethod object.|
|Create shipmentMethod|shipmentMethod|Create a shipmentMethod object.|
|Update shipmentMethod|shipmentMethod|Update a shipmentMethod object.|
|Delete shipmentMethod|none|Delete a shipmentMethod object.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the shipmentMethod. Read-Only.|
|code|string|Specifies the shipment method code.|
|displayName|string|Specifies the shipment method display name.|
|lastModifiedDateTime|datetime|The last datetime the shipment method was modified. Read-Only.|  


## Relationships
None

## JSON representation

Here is a JSON representation of the shipmentMethod.


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