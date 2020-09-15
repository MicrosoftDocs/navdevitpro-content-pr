---
title: agedAccountsReceivable resource type | Microsoft Docs
description: A aged accounts receivable object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/15/2020
ms.author: solsen
---

# agedAccountsReceivable resource type
Represents an aged accounts receivable in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method              | Return Type|Description               |
|:--------------------|:-----------|:-------------------------|
|[GET agedAccountsReceivable](../api/dynamics_agedAccountsReceivable_Get.md)|agedAccountsReceivable|Gets a aged accounts receivable object.|
|[DELETE agedAccountsReceivable](../api/dynamics_agedAccountsReceivable_Delete.md)|agedAccountsReceivable|Deletes a aged accounts receivable object.|
|[POST agedAccountsReceivable](../api/dynamics_agedAccountsReceivable_Create.md)|agedAccountsReceivable|Creates a aged accounts receivable object.|
|[PATCH agedAccountsReceivable](../api/dynamics_agedAccountsReceivable_Update.md)|agedAccountsReceivable|Updates a aged accounts receivable object.|




## Navigation

| Navigation |Return Type| Description |    
|:----------|:----------|:-----------------|
|[customer](../resources/dynamics_customer.md)|customer |Gets the customer of the agedAccountsReceivable.|



## Navigation

| Navigation |Return Type| Description |
|:----------|:----------|:-----------------|
|[customer](../resources/dynamics_customer.md)|customer   |Gets the customer of the agedAccountsReceivable.|



## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|customerId|GUID|The unique ID of customer.  |
|customerNumber|string|The customer's number.|
|name|string|Represents the aged accounts receivable's name.|
|currencyCode|string|The default currency code for the aged accounts receivable.|
|balanceDue|decimal|Specifies total balance due.|
|currentAmount|decimal|Specifies the current balance.|
|period1Amount|decimal|Specifies balance in the first aging period.|
|period2Amount|decimal|Specifies balance in the second aging period.|
|period3Amount|decimal|Specifies balance in the third aging period.|
|agedAsOfDate|date|The period start date.|
|periodLengthFilter|string|Specifies the length of the periods.|


## JSON representation

Here is a JSON representation of the agedAccountsReceivable resource.


```json
{
   "customerId": "GUID",
   "customerNumber": "string",
   "name": "string",
   "currencyCode": "string",
   "balanceDue": "decimal",
   "currentAmount": "decimal",
   "period1Amount": "decimal",
   "period2Amount": "decimal",
   "period3Amount": "decimal",
   "agedAsOfDate": "date",
   "periodLengthFilter": "string"
}
```
## See also

[GET agedAccountsReceivable](../api/dynamics_agedAccountsReceivable_Get.md)
[DELETE agedAccountsReceivable](../api/dynamics_agedAccountsReceivable_Delete.md)
[POST agedAccountsReceivable](../api/dynamics_agedAccountsReceivable_Create.md)
[PATCH agedAccountsReceivable](../api/dynamics_agedAccountsReceivable_Update.md)

