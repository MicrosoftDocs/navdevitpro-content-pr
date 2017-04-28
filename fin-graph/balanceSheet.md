---
title: BalanceSheet resource type | Microsoft Docs
description: A BalanceSheet.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/03/2017
ms.author: solsen
---

# BalanceSheet resource type
Represents an balanceSheet resource type in [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET BalanceSheet](get-balanceSheet.md)|BalanceSheet|Get a BalanceSheet object|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|lineNumber|numeric|The balanceSheet item line number. Read-Only.|
|display|string, maximum size 250|The balanceSheet item display name. Read-Only.|
|balance|numeric|The balanceSheet item balance. Read-Only|
|lineType|string, maximum size 30|The balanceSheet item line type. Read-Only|
|indentation|numeric|The balanceSheet item indentation. Read-Only|
|dateFilter|date|The date filter used to calculate the balanceSheet items. Read-Only| 


## Relationships
None

## JSON representation

Here is a JSON representation of the resource.


```json
{
    "lineNumber": "int",
    "display": "string",
    "balance": "decimal",
    "lineType": "string",
    "indentation": "int",
    "dateFilter": "date"
}

```
## See Also
[Graph Reference](graph-reference.md)  
