---
title: Update purchaseInvoices | Microsoft Docs
description: Updates a purchase invoice object in Dynamics 365 for Financials.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/05/2018
ms.author: solsen
---

# Update purchaseInvoices
Update the properties of a purchase invoices object for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request

```
PATCH /financials/companies({id})/purchaseInvoices({id})
```

## Request headers
|Header        |Value                    |
|--------------|-------------------------|
|Authorization |Bearer {token}. Required.|
|Content-Type  |application/json         |
|If-Match      |Required. When this request header is included and the eTag provided does not match the current tag on the **purchaseInvoices**, the **purchaseInvoices** will not be updated. |

## Request body
In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

## Response
If successful, this method returns a ```200 OK``` response code and an updated **purchaseInvoices** object in the response body.

## Example

**Request**

Here is an example of the request.
```json
PATCH https://api.financials.dynamics.com/v1.0/api/beta/companies({id})/purchaseInvoices({id})
Content-type: application/json

{
  "paymentTerms": "COD"
}
```

**Response**

Here is an example of the response. 

> [!NOTE]  
>   The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
HTTP/1.1 200 OK
Content-type: application/json

{
  "id": "id-value",
  "number": "1009",
  "invoiceDate": "2015-12-31",
  "dueDate": "2016-01-31",
  "vendorInvoiceNumber": "",
  "vendorId": "vendorId-value",
  "vendorNumber": "GL00000008",
  "vendorName": "GL00000008",
  "buyFromAddress": {
    "street": "",
    "city": "",
    "state": "",
    "countryLetterCode": "",
    "postalCode": ""
  },
  "currencyCode": "GBP",
  "paymentTerms": "COD",
  "shipmentMethod": "",
  "pricesIncludeTax": false,
  "discountAmount": 0,
  "discountAppliedBeforeTax": true,
  "totalAmountExcludingTax": 6825.6,
  "totalTaxAmount": 682.56,
  "totalAmountIncludingTax": 7508.16,
  "status": "Draft",
  "lastModifiedDateTime": "2017-03-17T19:02:22.043Z"
}
```

## See also
[Graph Reference](../api/dynamics_graph_reference.md)  
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[Purchase invoice](../resources/dynamics_purchaseinvoice.md)  
[Get purchase invoice](../api/dynamics_purchaseinvoice_get.md)  
[Create purchase invoice](../api/dynamics_create_purchaseinvoice.md)  
[Delete purchase invoice](../api/dynamics_purchaseinvoice_delete.md)  