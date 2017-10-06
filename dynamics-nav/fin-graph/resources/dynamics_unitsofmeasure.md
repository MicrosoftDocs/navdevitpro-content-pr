---
title: unitsOfMeasure resource type | Microsoft Docs
description: A unit of measure object in Dynamics 365 for Financials.
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

# unitsOfMeasure resource type

Represents a unit of measure, which is a standard of measurement of a quantity, in Dynamics 365 for Financials.

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET unitsOfMeasure](../api/dynamics_unitsofmeasure_get.md)|unitsOfMeasure|Gets a unit of measure object.|
|[POST unitsOfMeasure](../api/dynamics_create_unitsofmeasure.md)|unitsOfMeasure|Creates a unit of measure object.|
|[PATCH unitsOfMeasure](../api/dynamics_unitsofmeasure_update.md)|unitsOfMeasure|Updates a unit of measure object.|
|[DELETE unitsOfMeasure](../api/dynamics_unitsofmeasure_delete.md)|none|Deletes a unit of measure object.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the unitsOfMeasure. Non-editable.|
|code|string|Specifies the code for the unit of measure.|
|displayName|string|Specifies the unit of measure's display name.|
|internationalStandardCode|string|Specifies the unit of measure code expressed according to the UNECE Rec20 standard in connection with electronic sending of sales documents.|
|lastModifiedDateTime|datetime|The last datetime the unit of measure was modified. Read-Only.|  


## Relationships
None

## JSON representation

Here is a JSON representation of the **unitsOfMeasure** resource.

```json
{
  "id": "GUID",
  "code": "string",
  "displayName": "string",
  "internationalStandardCode": "string",
  "lastModifiedDateTime": "datetime"
}

```

## See also

- [Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 
