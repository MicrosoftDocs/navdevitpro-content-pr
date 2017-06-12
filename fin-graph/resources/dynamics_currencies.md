---
title: Currency resource type | Microsoft Docs
description: A Currency object.
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

# Currency resource type
Represents a currency used in Dynamics 365 for Financials.

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET currencies](../api/dynamics_get_currencies.md)|currencies|Get a Currency.|
|[POST currencies](../api/dynamics_create_currencies.md)|currencies|Create a Currency.|
|[PATCH currencies](../api/dynamics_update_currencies.md)|currencies|Update a Currency.|
|[DELETE currencies](../api/dynamics_delete_currencies.md)|none|Delete a Currency.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the currency. Non-editable.|
|code|string|Specifies the currency code. |
|displayName|string|Specifies the currency display name.|
|symbol|string|Specifies the symbol for this currency that appears on checks.|
|amountDecimalPlaces|string|Specifies the number of decimal places the system will display on amounts for this currency.|
|amountRoundingPrecision|decimal|Specifies the size of the interval to be used when rounding amounts for this currency.|
|lastModifiedDateTime|datetime|The last datetime the currency was modified. Read-Only.|  


## Relationships
None

## JSON representation

Here is a JSON representation of the currencies.


```json
{
  "id": "GUID",
  "code": "string",
  "displayName": "string",
  "symbol": "sring",
  "amountDecimalPlaces": "string",
  "amountRoundingPrecision": "decimal",
  "lastModifiedDateTime": "datetime"
}

```

## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 
