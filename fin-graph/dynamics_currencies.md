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
Represents a currencies resource type in [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET currencies](get-currencies.md)|currencies|Get a Currency.|
|[POST currencies](create-currencies.md)|currencies|Create a Currency.|
|[PATCH currencies](update-currencies.md)|currencies|Update a Currency.|
|[DELETE currencies](delete-currencies.md)|none|Delete a Currency.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the currency. Read-Only.|
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

## See Also
[Graph Reference](graph-reference.md)  