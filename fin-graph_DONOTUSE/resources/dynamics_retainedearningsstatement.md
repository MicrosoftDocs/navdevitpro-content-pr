---
title: retainedEarningsStatement resource type | Microsoft Docs
description: A RetainedEarningsStatement.
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

# retainedEarningsStatement resource type
Represents an retained earnings statement in Dynamics 365 for Financials.

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET retainedEarningsStatement](../api/dynamics_get_retainedearningsstatement.md)|RetainedEarningsStatement|Get a RetainedEarningsStatement object|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|lineNumber|numeric|The retainedEarningsStatement item line number.|
|display|string|The retainedEarningsStatement item display name.|
|netChange|numeric|The retainedEarningsStatement item Net Change.|
|lineType|string|The retainedEarningsStatement item line type can be: header, detail, total, or spacer.|
|indentation|numeric|The retainedEarningsStatement item indentation used in report layout.|
|dateFilter|date|The date filter used to calculate the retainedEarningsStatement items.|


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
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 
