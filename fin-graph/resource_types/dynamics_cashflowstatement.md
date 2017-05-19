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

# Cash flow statement resource type
Represents an cashFlowStatement resource type in Dynamics 365 for Financials.

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET cashFlowStatement](../api/dynamics_get_cashflowstatement.md)|CashFlowStatement|Get a CashFlowStatement object|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|lineNumber|numeric|The cashFlowStatement item line number.|
|display|string|The cashFlowStatement item display name.|
|netChange|numeric|The cashFlowStatement item Net Change.|
|lineType|string|The cashFlowStatement item line type can be: header, detail, total, or spacer.|
|indentation|numeric|The cashFlowStatement item indentation used in report layout.|
|dateFilter|date|The date filter used to calculate the cashFlowStatement items.|


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
