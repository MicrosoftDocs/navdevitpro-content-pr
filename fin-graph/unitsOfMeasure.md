---
title: Unit of Measure resource type | Microsoft Docs
description: An Unit of Measure.
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

# Unit of Measure resource type

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[Get unitsOfMeasure](get-unitsOfMeasure.md)|unitsOfMeasure|Get an unitsOfMeasure object.|
|[Create unitsOfMeasure](create-unitsOfMeasure.md)|unitsOfMeasure|Create an unitsOfMeasure object.|
|[Update unitsOfMeasure](update-unitsOfMeasure.md)|unitsOfMeasure|Update an unitsOfMeasure object.|
|[Delete unitsOfMeasure](delete-unitsOfMeasure.md)|none|Delete an unitsOfMeasure object.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the unitsOfMeasure. Read-Only.|
|code|string|Specifies the code for the Unit of Measure.|
|displayName|string|Specifies the Unit of Measure's display name.|
|internationalStandardCode|string|Specifies the unit of measure code expressed according to the UNECERec20 standard in connection with electronic sending of sales documents.|
|lastModifiedDateTime|datetime|The last datetime the unitsOfMeasure was modified. Read-Only.|  


## Relationships
None

## JSON representation

Here is a JSON representation of the unitsOfMeasure.

```json
{
  "id": "GUID",
  "code": "string",
  "displayName": "string",
  "internationalStandardCode": "string",
  "lastModifiedDateTime": "datetime"
}

```

## See Also
[Graph Reference](graph-reference.md)  