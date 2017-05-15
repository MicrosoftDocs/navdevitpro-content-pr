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
Represents a unitsOfMeasure resource type in Dynamics 365 for Financials.

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET unitsOfMeasure](../api/dynamics_get_unitsofmeasure.md)|unitsOfMeasure|Get a Unit of Measure.|
|[POST unitsOfMeasure](../api/dynamics_create_unitsofmeasure.md)|unitsOfMeasure|Create a Unit of Measure.|
|[PATCH unitsOfMeasure](../api/dynamics_update_unitsofmeasure.md)|unitsOfMeasure|Update a Unit of Measure.|
|[DELETE unitsOfMeasure](../api/dynamics_delete_unitsofmeasure.md)|none|Delete a Unit of Measure.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the unitsOfMeasure. Read-Only.|
|code|string|Specifies the code for the Unit of Measure.|
|displayName|string|Specifies the Unit of Measure's display name.|
|internationalStandardCode|string|Specifies the unit of measure code expressed according to the UNECE Rec20 standard in connection with electronic sending of sales documents.|
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
[Graph Reference](../api/dynamics_graph_reference.md)  
