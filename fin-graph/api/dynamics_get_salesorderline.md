---
title: GET Sales Order Line method | Microsoft Docs
description: Gets a sales order line.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/08/2017
ms.author: solsen
---

# GET Sales Order Line Method
Retrieve the properties and relationships of a sales order line object for Dynamics 365 for Financials.

## Prerequisites

## HTTP request

```
GET /financials/companies/{id}/salesOrders/{id}/salesOrderLines(documentId={id},sequence={number})
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and salesOrderLine object in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://graph.microsoft.com/beta/financials/companies/{id}/salesOrders/{id}/salesOrderLines(documentId={id},sequence={number})
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
  "documentId": "id-value",
  "sequence": 10000,
  "itemId": "id-value",
  "accountId": "id-value",
  "lineType": "Item",
  "lineDetails": {
    "number": "GL000091",
    "displayName": "GL000091",
    "description": null
  },
  "description": "GL00000091",
  "unitOfMeasure": {
    "code": "BOX",
    "displayName": "Box",
    "symbol": null,
    "unitConversion": null
  },
  "quantity": 96,
  "unitPrice": 71.1,
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
  "shipmentDate": "2019-01-24",
  "shippedQuantity": 0,
  "invoicedQuantity": 0,
  "invoiceQuantity": 96,
  "shipQuantity": 96
}
```

## See Also
[Microsoft Graph Reference](../api/dynamics_graph_reference.md)  
