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

# Income statement resource type
Represents an incomeStatement resource type in Dynamics 365 for Financials.

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET incomeStatement](../api/dynamics_get_incomestatement.md)|IncomeStatement|Get an IncomeStatement object|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|lineNumber|numeric|The incomeStatement item line number.|
|display|string|The incomeStatement item display name.|
|netChange|numeric|The incomeStatement item Net Change.|
|lineType|string|The incomeStatement item line type can be: header, detail, total, or spacer.|
|indentation|numeric|The incomeStatement item indentation used in report layout.|
|dateFilter|date|The date filter used to calculate the incomeStatement items.|


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
## See also
[Working with Dynamics 365 for Finance and Operations, Business Edition in Microsoft Graph](../resource_types/dynamics_overview.md) 
