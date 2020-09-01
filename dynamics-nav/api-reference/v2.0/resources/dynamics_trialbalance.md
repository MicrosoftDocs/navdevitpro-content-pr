---
title: trialBalance resource type | Microsoft Docs
description: A trial balance object in Dynamics 365 Business Central. 
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# trialBalance resource type
Represents a trial balance in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET trialBalance](../api/dynamics_trialbalance_get.md)|trialBalance|Gets a trial balance object.|


## Navigation

| Navigation |Return Type| Description |
|:----------|:----------|:-----------------|
|[account](../resources/dynamics_account.md)|account   |Gets the account of the trialBalance.|



## Properties

| Property     | Type   |Description|
|:---------------|:--------|:----------|
|number|string|The G/L Account number for the trialBalance item|
|display|string|The G/L Account name for the trialBalance item.|
|totalDebit|string|Represents total debit amount in G/L Account.|
|totalCredit|string|Represents total credit amount in G/L Account.|
|balanceAtDateDebit|string|Represents positive Balance at Date amount in G/L Account.|
|balanceAtDateCredit|string|Represents negative Balance at Date amount in G/L Account.|
|dateFilter|date|The date filter used to calculate the trialBalance items.|


## JSON representation

Here is a JSON representation of the resource.


```json
{
   "accountId": "GUID",
   "number": "string",
   "accountType": "string",
   "display": "string",
   "totalDebit": "string",
   "totalCredit": "string",
   "balanceAtDateDebit": "string",
   "balanceAtDateCredit": "string",
   "dateFilter": "date"
}
```
## See also

[Get Trial Balance](../api/dynamics_trialbalance_get.md)  