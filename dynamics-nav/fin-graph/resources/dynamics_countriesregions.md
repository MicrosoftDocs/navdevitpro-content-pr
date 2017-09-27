---
title: countriesRegions resource type | Microsoft Docs
description: A Countries/Regions object in Dynamics 365 for Financials. 
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

# countriesRegions resource type
Represents a countriesRegions object in Dynamics 365 for Financials, which is part of an address.

## Methods

| Method                                                              | Return Type    |Description                |
|:--------------------------------------------------------------------|:---------------|:--------------------------|
|[GET countriesRegions](../api/dynamics_countriesregions_get.md)      |countriesRegions|Get a Countries/Regions.   |
|[POST countriesRegions](../api/dynamics_create_countriesregions.md)  |countriesRegions|Create a Countries/Regions.|
|[PATCH countriesRegions](../api/dynamics_countriesregions_update.md) |countriesRegions|Update a Countries/Regions.|
|[DELETE countriesRegions](../api/dynamics_countriesregions_delete.md)|none            |Delete a Countries/Regions.|

## Properties
| Property	     | Type	      |Description                                                  |
|:---------------|:-----------|:------------------------------------------------------------|
|id              |GUID        |The unique ID of the country/region. Non-editable.           |
|code            |string      |Specifies the code of the country/region.                    |
|displayName     |string      |Specifies the display name of the country/region.            |
|addressFormat   |string      |Specifies the format of the address that is displayed on external-facing documents. You link an address format to a country/region code so that external-facing documents based on cards or documents with that country/region code use the specified address format.|
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

## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 
