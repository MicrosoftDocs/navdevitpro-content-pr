---
title: Sales Quote resource type | Microsoft Docs
description: A Sales Quote.
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

# Sales quote resource type
Represents a salesQuote resource type in Dynamics 365 for Financials.

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET Sales Quote](../api/dynamics_get_salesquote.md)|Sales Quote|Get a Sales Quote object|
|[POST Sales Quote](../api/dynamics_create_salesquote.md)|Sales Quote|Create a Sales Quote object|
|[PATCH Sales Quote](../api/dynamics_update_salesquote.md)|Sales Quote|Update a Sales Quote object|
|[DELETE Sales Quote](../api/dynamics_delete_salesquote.md)|none|Delete a Sales Quote object|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The quote ID. Read-Only.|
|number|string, maximum size 20|The quote number. Read-Only.|
|documentDate|date|The quote date|
|dueDate|date|The quote due date|
|customerId|GUID|The id of the quote customer.|
|contactId|string, maximum size 250|The exchange contact id for the given customer. If a customer id is not specified, we will use the contact id to find it.|
|customerNumber|string, maximum size 20|The customer number for the quote.|
|customerName|string, maximum size 50|The full name of the customer. Read-Only.|
|billingPostalAddress|complex|The billing postal address for the quote.|  
|currencyCode|string, maximum size 10|The currency code for the quote.|
|paymentTerms|string, maximum size 10|The payment terms of the quote.|
|shipmentMethod|string, maximum size 10|The payment terms of the quote.|
|salesperson|string, maximum size 20|The salesperson code for the quote.|
|discountAmount|numeric|The quote discount amount|
|totalAmountExcludingTax|numeric|The total amount excluding tax. Read-Only.|
|totalTaxAmount|numeric|The total tax amount for the quote. Read-Only.|
|totalAmountIncludingTax|numeric|The total amount for the quote, including tax. Read-Only.|
|status|string, maximum size 20|The quote status. Status can be: Open,Released,Pending Approval,Pending Prepayment. Read-Only.|
|lastModifiedDateTime|datetime|The last datetime the sales quote was modified. Read-Only.|


## Relationships
A Currency(currencyCode) must exist in the Currencies table.

A Payment Term(paymentTerms) must exist in the Payment Terms table.

A Shipment Method(shipmentMethod) must exist in the Shipment Method table.

A Customer (customerId) must exist in the Customer table.

## JSON representation

Here is a JSON representation of the resource.


```json
{
      "id": "GUID",
      "number": "string",
      "documentDate": "Date",
      "dueDate": "Date",
      "customerId": "GUID",
      "contactId": "string",
      "customerNumber": "string",
      "customerName": "string",
      "billingPostalAddress": {NAV.PostalAddress},
      "currencyCode": "string",
      "paymentTerms": "string",
      "shipmentMethod": "string",
      "salesperson": "string",
      "discountAmount": decimal,
      "totalAmountExcludingTax": decimal,
      "totalTaxAmount": decimal,
      "totalAmountIncludingTax": decimal,
      "status": "string",
      "lastModifiedDateTime": "DateTime"
}

```
## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 
