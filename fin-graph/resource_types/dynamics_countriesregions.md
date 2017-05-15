---
title: Countries/Regions resource type | Microsoft Docs
description: A Countries/Regions.
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

# Countries/Regions resource type
Represents a countriesRegions resource type in Dynamics 365 for Financials.

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET countriesRegions](../api/dynamics_get_countriesregions.md)|countriesRegions|Get a Countries/Regions.|
|[POST countriesRegions](../api/dynamics_create_countriesregions.md)|countriesRegions|Create a Countries/Regions.|
|[PATCH countriesRegions](../api/dynamics_update_countriesregions.md)|countriesRegions|Update a Countries/Regions.|
|[DELETE countriesRegions](../api/dynamics_delete_countriesregions.md)|none|Delete a Countries/Regions.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the country/region. Read-Only.|
|code|string|Specifies the code of the country/region.|
|displayName|string|Specifies the display name of the country/region.|
|addressFormat|string|Specifies the format of the address that is displayed on external-facing documents. You link an address format to a country/region code so that external-facing documents based on cards or documents with that country/region code use the specified address format.|
|lastModifiedDateTime|datetime|The last datetime the country/region was modified. Read-Only.|  


## Relationships
None

## JSON representation

Here is a JSON representation of the countriesRegions.


```json
{
  "id": "GUID",
  "code": "string",
  "displayName": "string",
  "addressFormat": "string",
  "lastModifiedDateTime": "datetime"
}

```

## See Also
[Graph Reference](../api/dynamics_graph_reference.md)  
