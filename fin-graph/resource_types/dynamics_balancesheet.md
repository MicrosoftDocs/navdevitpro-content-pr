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

# Balance sheet resource type
Represents a balanceSheet resource type in Dynamics 365 for Financials.

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET balanceSheet](../api/dynamics_get_balancesheet.md)|BalanceSheet|Get a BalanceSheet object|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|lineNumber|numeric|The balanceSheet item line number.|
|display|string|The balanceSheet item display name.|
|balance|numeric|The balanceSheet item balance.|
|lineType|string|The balanceSheet item line type can be: header, detail, total, or spacer.|
|indentation|numeric|The balanceSheet item indentation used in report layout.|
|dateFilter|date|The date filter used to calculate the balanceSheet items.|


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
## See also
[Working with Dynamics 365 for Finance and Operations, Business Edition in Microsoft Graph](dynamics_overview.md)  
