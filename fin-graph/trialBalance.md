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

# TrialBalance resource type
Represents an trialBalance resource type in [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET TrialBalance](get-trialBalance.md)|TrialBalance|Get a TrialBalance object|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|number|string, maximum size 20|The G/L Account number for the trialBalance item. Read-Only.|
|display|string, maximum size 50|The G/L Account name for the trialBalance item. Read-Only.|
|netChangeDebit|string, maximum size 30|Represents positive Net Change amount in G/L Account. Read-Only|
|netChangeCredit|string, maximum size 30|Represents negative Net Change amount in G/L Account. Read-Only|
|balanceAtDateDebit|string, maximum size 30|Represents positive Balance at Date amount in G/L Account. Read-Only|
|balanceAtDateCredit|string, maximum size 30|Represents negative Balance at Date amount in G/L Account. Read-Only|
|dateFilter|date|The date filter used to calculate the trialBalance items. Read-Only| 


## Relationships
None

## JSON representation

Here is a JSON representation of the resource.


```json
{
    "number": "string",
    "display": "string",
    "netChangeDebit": "decstringimal",
    "netChangeCredit": "string",
    "balanceAtDateDebit": "string",
    "balanceAtDateCredit": "string",
    "dateFilter": "date"
}

```
## See Also
[Graph Reference](graph-reference.md)  
