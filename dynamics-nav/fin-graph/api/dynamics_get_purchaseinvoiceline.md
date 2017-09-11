---
title: GET Purchase Invoice Line method | Microsoft Docs
description: Gets a purchase invoice line.
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

# Get purchaseInvoiceLines
Retrieve the properties and relationships of a purchase invoice line object for Dynamics 365 for Financials.

## Prerequisites

## HTTP request

```
GET /financials/companies/({id})/purchaseInvoices/({id})/purchaseInvoiceLines(documentId=({id}),sequence=({number}))
```

## Request headers
|Header         |Value                     |
|---------------|--------------------------|
|Authorization  |Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and purchaseInvoiceLine object in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://api.financials.dynamics.com/v1.0/api/beta/companies/({id})/purchaseInvoices/({id})/purchaseInvoiceLines(documentId=({id}),sequence=({number}))
```

**Response**

Here is an example of the response. 

> [!NOTE]  
>   The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
  "documentId": "id-value",
  "sequence": 10000,
  "itemId": "id-value",
  "accountId": "id-value",
  "lineType": "Item",
  "lineDetails": {
    "number": "GL000009",
    "displayName": "GL000009"
  },
  "description": "someText",
  "unitOfMeasure": {
    "code": "BOX",
    "displayName": "Box",
    "symbol": null,
    "unitConversion": null
  },
  "unitCost": 71.1,
  "quantity": 96,
  "discountAmount": 0,
  "discountPercent": 0,
  "discountAppliedBeforeTax": false,
  "amountExcludingTax": 6825.6,
  "taxCode": "VAT10",
  "taxPercent": 10,
  "totalTaxAmount": 682.56,
  "amountIncludingTax": 7508.16,
  "invoiceDiscountAllocation": 0,
  "netAmount": 6825.6,
  "netTaxAmount": 682.56,
  "netAmountIncludingTax": 7508.16,
  "expectedReceiptDate": "2015-02-24"
}
```

## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 
