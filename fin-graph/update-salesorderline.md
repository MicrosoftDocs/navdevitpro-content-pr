---
title: PATCH Sales Order Line method | Microsoft Docs
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

# PATCH Sales Order Line Method
Update the properties of a salesOrderLine object for [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].

## HTTP request

```
PATCH /financials/companies/{id}/salesOrders/{id}/salesOrderLines(documentId={id},sequence={number})
```

## Request headers
|Header|Value|
|------|-----|
|Authorization |Bearer. Required.|
|Content-Type  |application/json|
|If-Match      |Required. When this request header is included and the eTag provided does not match the current tag on the salesOrderLine, the salesOrderLine will not be updated. |

## Request body
In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

## Response
If successful, this method returns a ```200 OK``` response code and an updated salesOrderLine object in the response body.

## Example

**Request**

Here is an example of the request.
```json
PATCH https://graph.microsoft.com/beta/financials/companies/{id}/salesOrders{id}/salesOrderLines(documentId={id},sequence={number})
Content-type: application/json

{
  "description": "someText"
}
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
HTTP/1.1 200 OK
Content-type: application/json

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
  "description": "someText",
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
[Microsoft Graph Reference](graph-reference.md)  
