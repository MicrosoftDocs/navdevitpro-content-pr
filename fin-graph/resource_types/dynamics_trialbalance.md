---
title: TrialBalance resource type | Microsoft Docs
description: A TrialBalance.
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

# Trial balance resource type
Represents an trialBalance resource type in Dynamics 365 for Financials.

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET trialBalance](../api/dynamics_get_trialbalance.md)|TrialBalance|Get a TrialBalance object|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|number|string|The G/L Account number for the trialBalance item|
|display|string|The G/L Account name for the trialBalance item.|
|netChangeDebit|string|Represents positive Net Change amount in G/L Account.|
|netChangeCredit|string|Represents negative Net Change amount in G/L Account.|
|balanceAtDateDebit|string|Represents positive Balance at Date amount in G/L Account.|
|balanceAtDateCredit|string|Represents negative Balance at Date amount in G/L Account.|
|dateFilter|date|The date filter used to calculate the trialBalance items.|


## Relationships
None

## JSON representation

Here is a JSON representation of the resource.


```json
{
    "number": "string",
    "display": "string",
    "netChangeDebit": "string",
    "netChangeCredit": "string",
    "balanceAtDateDebit": "string",
    "balanceAtDateCredit": "string",
    "dateFilter": "date"
}

```
## See also
[Graph Reference](../api/dynamics_graph_reference.md)  
