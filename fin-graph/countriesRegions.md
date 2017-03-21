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

# countriesRegions resource type
Represents a countriesRegions resource type in [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[Get countriesRegions](get-countriesRegions.md)|countriesRegions|Get a countriesRegions object.|
|[Create countriesRegions](create-countriesRegions.md)|countriesRegions|Create a countriesRegions object.|
|[Update countriesRegions](update-countriesRegions.md)|countriesRegions|Update a countriesRegions object.|
|[Delete countriesRegions](delete-countriesRegions.md)|none|Delete a countriesRegions object.|

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
[Graph Reference](graph-reference.md)  