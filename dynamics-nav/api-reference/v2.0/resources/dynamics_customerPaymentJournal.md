---
title: customerPaymentJournal resource type | Microsoft Docs
description: A customer payments journal in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# customerPaymentJournal resource type
Represents a customer payments journal in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method               | Return Type             |Description                      |
|:---------------------|:------------------------|:--------------------------------|
|[GET customerPaymentJournal](../api/dynamics_customerpaymentsjournal_get.md)      |customerPaymentJournal|Gets a customer payments journal.   |
|[POST customerPaymentJournal](../api/dynamics_create_customerpaymentsjournal.md)  |customerPaymentJournal|Creates a customer payments journal.|
|[PATCH customerPaymentJournal](../api/dynamics_customerpaymentsjournal_update.md) |customerPaymentJournal|Updates a customer payments journal.|
|[DELETE customerPaymentJournal](../api/dynamics_customerpaymentsjournal_delete.md)|none                     |Deletes a customer payments journal.|


## Navigation

| Navigation |Return Type| Description |
|:----------|:----------|:-----------------|
|[account](../resources/dynamics_account.md)|account   |Gets the account of the customerPaymentJournal.|
|[customerPayments](../resources/dynamics_customerpayments.md)|customerPayments   |Gets the customerpayments of the customerPaymentJournal.|



## Properties

| Property           | Type                  |Description                                                             |
|:-------------------|:----------------------|:-----------------------------------------------------------------------|
|id                  |GUID                   |The unique ID of the customer payments journal. Non-editable.           |
|code                |string, maximum size 10| The code of the customer payments journal.                             |
|displayName         |string, maximum size 50| The display name of the customer payments journal.                     |
|lastModifiedDateTime|datetime               |The last datetime the customer payments journal was modified. Read-Only.|

## JSON representation

Here is a JSON representation of the resource.


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
[Microsoft Graph Reference](../api/dynamics_graph_reference.md)  
  
[Customer Payments Journal](../api/dynamics_customerpaymentsjournal_get.md)  
[Post Customer Payments Journal](../api/dynamics_create_customerpaymentsjournal.md)  
[Patch Customer Payments Journal](../api/dynamics_customerpaymentsjournal_update.md)  
[Delete Customer Payments Journal](../api/dynamics_customerpaymentsjournal_delete.md)  
