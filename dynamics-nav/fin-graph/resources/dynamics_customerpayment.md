---
title: customerPayment resource type | Microsoft Docs
description: A customer payment.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/11/2017
ms.author: solsen
---

# customerPayment resource type
Represents a customer payment in Dynamics 365 for Financials.

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET customerPayment](../api/dynamics_get_customerpayment.md)|customerPayments|Get Customer Payment.|
|[POST customerPayment](../api/dynamics_create_customerpayment.md)|customerPayments|Create Customer Payment.|
|[PATCH customerPayment](../api/dynamics_update_customerpayment.md)|customerPayments|Update Customer Payment.|
|[DELETE customerPayment](../api/dynamics_delete_customerpayment.md)|none|Delete Customer Payment.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
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


## Relationships
A customer payment is a subpage of a customer payments journal. It cannot be accessed directly.

A customer payment can be a "Parent Entity" of the dimension lines.

A Customer (customerId) must exist in the Customers table.

An Invoice (appliesToInvoiceId) must exist in the Sales Invoices Table.


## JSON representation

Here is a JSON representation of the resource.

```json
{
    "id": "GUID",
    "lineNumber": integer,
    "customerId": "GUID",
    "customerNumber": "string",
    "contactId": "string",
    "postingDate": "date",
    "documentNumber": "string",
    "externalDocumentNumber": "string",
    "amount": decimal,
    "appliesToInvoiceId": "GUID",
    "appliesToInvoiceNumber": "string",
    "description": "string",
    "comment": "string",
    "lastModifiedDateTime": "datetime"
}
```

## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 
