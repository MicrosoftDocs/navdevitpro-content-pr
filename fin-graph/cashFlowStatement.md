---
title: CashFlowStatement resource type | Microsoft Docs
description: A CashFlowStatement.
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

# CashFlowStatement resource type
Represents an cashFlowStatement resource type in [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET CashFlowStatement](get-cashFlowStatement.md)|CashFlowStatement|Get a CashFlowStatement object|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|lineNumber|numeric|The cashFlowStatement item line number. Read-Only.|
|display|string, maximum size 250|The cashFlowStatement item display name. Read-Only.|
|netChange|numeric|The cashFlowStatement item Net Change. Read-Only|
|lineType|string, maximum size 30|The cashFlowStatement item line type. Read-Only|
|indentation|numeric|The cashFlowStatement item indentation. Read-Only|
|dateFilter|date|The date filter used to calculate the cashFlowStatement items. Read-Only| 


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
