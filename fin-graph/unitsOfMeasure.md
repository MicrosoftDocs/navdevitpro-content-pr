---
title: unitsOfMeasure resource type | Microsoft Docs
description: An unitsOfMeasure.
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

# unitsOfMeasure resource type

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|Get unitsOfMeasure|unitsOfMeasure|Get an unitsOfMeasure object.|
|Create unitsOfMeasure|unitsOfMeasure|Create an unitsOfMeasure object.|
|Update unitsOfMeasure|unitsOfMeasure|Update an unitsOfMeasure object.|
|Delete unitsOfMeasure|none|Delete an unitsOfMeasure object.|

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


```
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