---
title: AgedAccountsReceivable resource type | Microsoft Docs
description: A AgedAccountsReceivable.
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

# AgedAccountsReceivable resource type
Represents an agedAccountsReceivable resource type in [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET AgedAccountsReceivable](get-agedAccountsReceivable.md)|AgedAccountsReceivable|Get AgedAccountsReceivable object|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|customerId|GUID|The unique ID of customer. Read-Only.|
|customerNumber|string, maximum size 20|Specifies customer's number. Read-Only.|
|name|string, maximum size 50|Specifies customer's name. Read-Only|
|currencyCode|string, maximum size 10|Specifies the currency. Read-Only|
|before|numeric|Specifies balance before first aging period. Read-Only|
|period1|numeric|Specifies balance in the first aging period. Read-Only|
|period2|numeric|Specifies balance in the second aging period. Read-Only|
|period3|numeric|Specifies balance in the third aging period. Read-Only|
|after|numeric|Specifies balance after third aging period. Read-Only|
|balance|numeric|Specifies customer's total balance. Read-Only|
|periodStartDateFilter|date|Specifies period start date used to calculate aging periods. Read-Only|
|periodLengthFilter|string, maximum size 10|Specifies the length of the periods. Read-Only|


## Relationships
None

## JSON representation

Here is a JSON representation of the resource.


```json
{
    "customerId": "GUID",
    "customerNumber": "string",
    "name": "string",
    "currencyCode": "string",
    "before": "decimal",
    "period1": "decimal",
    "period2": "decimal",
    "period3": "decimal",
    "after": "decimal",
    "balance": "decimal",
    "periodStartDateFilter": "date",
    "periodLengthFilter": "string
}

```
## See Also
[Graph Reference](graph-reference.md)  
