---
title: IncomeStatement resource type | Microsoft Docs
description: A IncomeStatement.
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

# IncomeStatement resource type
Represents an incomeStatement resource type in [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET IncomeStatement](get-incomeStatement.md)|IncomeStatement|Get an IncomeStatement object|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|lineNumber|numeric|The incomeStatement item line number. Read-Only.|
|display|string, maximum size 250|The incomeStatement item display name. Read-Only.|
|netChange|numeric|The incomeStatement item Net Change. Read-Only|
|lineType|string, maximum size 30|The incomeStatement item line type. Read-Only|
|indentation|numeric|The incomeStatement item indentation. Read-Only|
|dateFilter|date|The date filter used to calculate the incomeStatement items. Read-Only| 


## Relationships
None

## JSON representation

Here is a JSON representation of the resource.


```json
{
    "lineNumber": "int",
    "display": "string",
    "netChange": "decimal",
    "lineType": "string",
    "indentation": "int",
    "dateFilter": "date"
}

```
## See Also
[Graph Reference](graph-reference.md)  
