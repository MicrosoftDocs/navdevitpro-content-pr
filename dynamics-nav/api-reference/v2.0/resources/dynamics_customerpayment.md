---
title: customerPayment resource type | Microsoft Docs
description: A customer payments object in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# customerPayment resource type
Represents a customer payment in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method         | Return Type  |Description|
|:---------------|:-------------|:----------|
|[GET customerPayment](../api/dynamics_customerpayment_get.md)|customerPayment|Gets a customer payment.|
|[POST customerPayment](../api/dynamics_create_customerpayment.md)|customerPayment|Creates a customer payment.|
|[PATCH customerPayment](../api/dynamics_customerpayment_update.md)|customerPayment|Updates a customer payment.|
|[DELETE customerPayment](../api/dynamics_customerpayment_delete.md)|none|Deletes a customer payment.|


## Navigation

| Navigation |Return Type| Description |
|:----------|:----------|:-----------------|
|[customer](../resources/dynamics_customer.md)|customer   |Gets the customer of the customerPayment.|



## Properties

| Property     | Type    |Description|
|:-------------|:--------|:----------|
|id|GUID|The unique ID of the customer payment. Non-editable.|
|lineNumber|integer|The number of the customer payment.|
|customerId|GUID|The unique ID of the customer that the payment is related to.|
|customerNumber|string, maximum size 20|The number of the customer that the payment is related to.|
|contactId|string, maximum size 250|The exchange contact id for the given customer. If a customer id is not specified, we will use the contact id to find it.|
|postingDate|date|The date that the customer payment is posted.|
|documentNumber|string, maximum size 20|Specifies a document number for the customer payment.|
|externalDocumentNumber|string, maximum size 20|Specifies an external document number for the customer payment.|
|amount|decimal|Specifies the total amount (including VAT) that the customer payment consists of.|
|appliesToInvoiceId|GUID|The unique ID of the invoice that the payment is related to.|
|appliesToInvoiceNumber|string, maximum size 20|The number of the invoice that the payment is related to.|
|description|string, maximum size 50|The description of the customer payment, provided by the user or autocreated.|
|comment|string, maximum size 250|A user specified comment on the customer payment.|
|lastModifiedDateTime|datetime|The last datetime the customer payment was modified. Read-Only.|


## JSON representation

Here is a JSON representation of the resource.

```json
{
   "id": "GUID",
   "journalDisplayName": "string",
   "lineNumber": "integer",
   "customerId": "GUID",
   "customerNumber": "string",
   "contactId": "string",
   "postingDate": "date",
   "documentNumber": "string",
   "externalDocumentNumber": "string",
   "amount": "decimal",
   "appliesToInvoiceId": "GUID",
   "appliesToInvoiceNumber": "string",
   "description": "string",
   "comment": "string",
   "dimensions": "dimensionType",
   "lastModifiedDateTime": "datetime"
}
```

## See also
  
[Get Customer Payments](../api/dynamics_customerpayment_get.md)  
[Post Customer Payments](../api/dynamics_create_customerpayment.md)  
[Patch Customer Payments](../api/dynamics_customerpayment_update.md)  
[Delete Customer Payments](../api/dynamics_customerpayment_delete.md)  
