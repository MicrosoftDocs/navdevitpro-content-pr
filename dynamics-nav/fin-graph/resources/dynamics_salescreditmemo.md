---
title: salesInvoice resource type | Microsoft Docs
description: A Sales Credit Memo.
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

# salesCreditMemo resource type
Represents a sales credit memo in Dynamics 365 for Financials. 

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET Sales Credit Memo](../api/dynamics_get_salescreditmemo.md)|Sales Credit Memo|Get a Sales Credit Memo object|
|[POST Sales Credit Memo](../api/dynamics_create_salescreditmemo.md)|Sales Credit Memo|Create a Sales Credit Memo object|
|[PATCH Sales Credit Memo](../api/dynamics_update_salescreditmemo.md)|Sales Credit Memo|Update a Sales Credit Memo object|
|[DELETE Sales Credit Memo](../api/dynamics_delete_salescreditmemo.md)|none|Delete a Sales Credit Memo object|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The credit memo ID. Non-editable.|
|number|string, maximum size 20|The credit memo number. Read-Only.|
|creditMemoDate|date|The credit memo date|
|dueDate|date|The date the credit memo is due.|
|customerId|GUID|The id of the credit memo customer.|
|contactId|string, maximum size 250|The exchange contact id for the given customer. If a customer id is not specified, we will use the contact id to find it.|
|customerNumber|string, maximum size 20|The customer number for the credit memo.|
|customerName|string, maximum size 50|The full name of the customer. Read-Only.|
|billingPostalAddress|complex|The billing postal address for the credit memo.|
|currencyId|GUID|The id of the credit memo currency.|
|currencyCode|string, maximum size 10|The currency code for the credit memo.|
|paymentTermsId|GUID|The id of the credit memo payment term.|
|paymentTerms|string, maximum size 10|The payment terms of the credit memo.|
|salesperson|string, maximum size 20|The salesperson code for the credit memo.|
|pricesIncludeTax|boolean|Specifies whether the prices include Tax or not. Read-Only.|
|discountAmount|numeric|The credit memo discount amount|
|discountAppliedBeforeTax|boolean|Specifies whether the discount is applied before tax.|
|totalAmountExcludingTax|numeric|The total amount excluding tax. Read-Only.|
|totalTaxAmount|numeric|The total tax amount for the credit memo. Read-Only.|
|totalAmountIncludingTax|numeric|The total amount for the credit memo, including tax. Read-Only.|
|status|string, maximum size 20|The credit memo status. Status can be: Draft, In Review, Open, Paid, Canceled, or Corrective. Read-Only.|
|lastModifiedDateTime|datetime|The last datetime the sales credit memo was modified. Read-Only.|
|invoiceId|GUID|The sales invoice ID that the credit memo is linked to.|
|invoiceNumber|GUID|The sales invoice number that the credit memo is linked to.|


## Relationships
A Currency (currencyCode) must exist in the Currencies table.

A Payment Term (paymentTerms) must exist in the Payment Terms table.

A Customer (customerId) must exist in the Customer table.

An Invoice (invoiceId) must exist in the Sales Invoice table.

## JSON representation

Here is a JSON representation of the resource.


```json
{
      "id": "GUID",
      "number": "string",
      "creditMemoDate": "Date",
      "dueDate": "Date",
      "customerId": "GUID",
      "contactId": "string",
      "customerNumber": "string",
      "customerName": "string",
      "billingPostalAddress": {NAV.PostalAddress},
      "currencyId": "GUID",
      "currencyCode": "string",
      "paymentTermsId": "GUID",
      "paymentTerms": "string",
      "salesperson": "string",
      "pricesIncludeTax": "boolean",
      "discountAmount": "decimal",
      "discountAppliedBeforeTax": "boolean",
      "totalAmountExcludingTax": "decimal",
      "totalTaxAmount": "decimal",
      "totalAmountIncludingTax": "decimal",
      "status": "string",
      "lastModifiedDateTime": "DateTime",
      "invoiceId" : "GUID",
      "invoiceNumber" : "string"
}

```
## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 
