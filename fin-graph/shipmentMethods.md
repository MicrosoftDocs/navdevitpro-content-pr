---
title: Shipment Method resource type | Microsoft Docs
description: A Shipment Method.
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

# Shipment Method resource type

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[Get shipmentMethod](get-shipmentMethods.md)|shipmentMethod|Get a shipmentMethod object.|
|[Create shipmentMethod](create-shipmentMethods.md)|shipmentMethod|Create a shipmentMethod object.|
|[Update shipmentMethod](update-shipmentMethods.md)|shipmentMethod|Update a shipmentMethod object.|
|[Delete shipmentMethod](delete-shipmentMethods.md)|none|Delete a shipmentMethod object.|

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
