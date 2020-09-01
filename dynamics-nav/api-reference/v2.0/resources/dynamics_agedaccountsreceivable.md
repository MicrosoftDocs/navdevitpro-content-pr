---
title: agedAccountsReceivable resource type | Microsoft Docs
description: An aged accounts receivable object in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# agedAccountsReceivable resource type
Represents an agedAccountsReceivable object in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)], which is showing the aging of a customer account.

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)], see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method         | Return Type  |Description|
|:---------------|:-------------|:----------|
|[GET agedAccountsReceivable](../api/dynamics_agedaccountsreceivable_get.md)|agedAccountsReceivable|Get agedAccountsReceivable object|


## Navigation

| Navigation |Return Type| Description |
|:----------|:----------|:-----------------|
|[customer](../resources/dynamics_customer.md)|customer   |Gets the customer of the agedAccountsReceivable.|



## Properties

| Property       | Type    |Description                                  |
|:---------------|:--------|:--------------------------------------------|
|customerId      |GUID     |The unique ID of customer.                   |
|customerNumber  |string   |Specifies customer's number.                 |
|name            |string   |Specifies customer's name.                   |
|currencyCode    |string   |Specifies the currency.                      |
|before          |numeric  |Specifies balance before first aging period. |
|period1         |numeric  |Specifies balance in the first aging period. |
|period2         |numeric  |Specifies balance in the second aging period.|
|period3         |numeric  |Specifies balance in the third aging period. |
|after           |numeric  |Specifies balance after third aging period.  |
|balance         |numeric  |Specifies customer's total balance.          |  
|periodStartDateFilter|date|Specifies period start date used to calculate aging periods.|
|periodLengthFilter|string |Specifies the length of the periods.         |


## JSON representation

Here is a JSON representation of the resource.


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
  
[Get Aged Accounts Receivable](../api/dynamics_agedaccountsreceivable_get.md)  
[Aged Accounts Payable](dynamics_agedaccountspayable.md)  
[Account](dynamics_account.md)  

