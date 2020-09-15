---
title: customerPaymentJournal resource type | Microsoft Docs
description: A customer payment journal object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/15/2020
ms.author: solsen
---

# customerPaymentJournal resource type
Represents an customer payment journal in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method              | Return Type|Description               |
|:--------------------|:-----------|:-------------------------|
|[GET customerPaymentJournal](../api/dynamics_customerPaymentJournal_Get.md)|customerPaymentJournal|Gets a customer payment journal object.|
|[DELETE customerPaymentJournal](../api/dynamics_customerPaymentJournal_Delete.md)|customerPaymentJournal|Deletes a customer payment journal object.|
|[POST customerPaymentJournal](../api/dynamics_customerPaymentJournal_Create.md)|customerPaymentJournal|Creates a customer payment journal object.|
|[PATCH customerPaymentJournal](../api/dynamics_customerPaymentJournal_Update.md)|customerPaymentJournal|Updates a customer payment journal object.|




## Navigation

| Navigation |Return Type| Description |    
|:----------|:----------|:-----------------|
|[account](../resources/dynamics_account.md)|account |Gets the account of the customerPaymentJournal.|
|[customerPayments](../resources/dynamics_customerpayments.md)|customerPayments |Gets the customerpayments of the customerPaymentJournal.|


## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|id|GUID|The unique ID of the item. Non-editable.|
|code|string|The code of the customer payment journal.|
|displayName|string|Specifies the customer payment journal's name. This name will appear on all sales documents for the customer payment journal.|
|lastModifiedDateTime|datetime|The last datetime the customer payment journal was modified. Read-Only.|
|balancingAccountId|GUID|The balancing G/L Account ID.|
|balancingAccountNumber|string|The balancing G/L Account number.|


## JSON representation

Here is a JSON representation of the customerPaymentJournal resource.


```json
{
   "id": "GUID",
   "code": "string",
   "displayName": "string",
   "lastModifiedDateTime": "datetime",
   "balancingAccountId": "GUID",
   "balancingAccountNumber": "string"
}
```
## See also

[GET customerPaymentJournal](../api/dynamics_customerPaymentJournal_Get.md)
[DELETE customerPaymentJournal](../api/dynamics_customerPaymentJournal_Delete.md)
[POST customerPaymentJournal](../api/dynamics_customerPaymentJournal_Create.md)
[PATCH customerPaymentJournal](../api/dynamics_customerPaymentJournal_Update.md)

