---
title: customer payment resource type | Microsoft Docs
description: A customer payment.
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

# Customer Payment resource type
Represents a customerPayment resource type in [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET customerPayment](get-customerpayment.md)|customerPayments|Get Customer Payment.|
|[POST customerPayment](create-customerpayment.md)|customerPayments|Create Customer Payment.|
|[PATCH customerPayment](update-customerpayment.md)|customerPayments|Update Customer Payment.|
|[DELETE customerPayment](delete-customerpayment.md)|none|Delete Customer Payment.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the customer payment. Read-Only.|
|lineNumber|integer|The number of the customer payment.|
|customerId|GUID|The unique ID of the customer that the payment is related to.|
|customerNumber|string, maximum size 20|The number of the customer that the payment is related to.|
|postingDate|date|The date that the customer payment is posted. Read-Only.|
|documentNumber|string, maximum size 20|Specifies a document number for the customer payment.|
|externalDocumentNumber|string, maximum size 20|Specifies an external document number for the customer payment.|
|amount|decimal|Specifies the total amount (including VAT) that the customer payment consists of.|
|appliesToInvoiceId|GUID|The unique ID of the invoice that the payment is related to.|
|appliesToInvoiceNumber|string, maximum size 20|The number of the invoice that the payment is related to.|
|description|string, maximum size 50|The description of the customer payment, provided by the user or autocreated.|
|comment|string, maximum size 250|A user specified comment on the customer payment.|
|financialDimension1|string, maximum size 20|Specifies the dimension 1 value code that the customer payment is linked to.|
|financialDimension2|string, maximum size 20|Specifies the dimension 2 value code that the customer payment is linked to.|
|lastModifiedDateTime|datetime|The last datetime the customer payment was modified. Read-Only.|


## Relationships
None

## JSON representation

Here is a JSON representation of the resource.


```json
{
"id": "GUID",
"lineNumber": integer,
"customerId": "GUID",
"customerNumber": "string",
"postingDate": "date",
"documentNumber": "string",
"externalDocumentNumber": "string",
"amount": decimal,
"appliesToInvoiceId": "GUID",
"appliesToInvoiceNumber": "string",
"description": "string",
"comment": "string",
"financialDimension1": "string",
"financialDimension2": "string",
"lastModifiedDateTime": "datetime"
}
```

## See Also
[Graph Reference](graph-reference.md)  
