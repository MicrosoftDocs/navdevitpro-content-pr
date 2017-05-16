---
title: GET customer method | Microsoft Docs
description: Gets a customer.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/13/2017
ms.author: solsen
---

# Get customer
Retrieve the properties and relationships of a customer object for Dynamics 365 for Financials.

## HTTP request
```
GET /financials/companies/{id}/customers/{id}
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and customers object in the response body.

**Request**

Here is an example of the request.

```json
GET https://graph.microsoft.com/beta/financials/companies/{id}/customers/{id}
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
  "id": "id-value",
  "number": "10000",
  "displayName": "Coho Winery",
  "address": {
    "street": "192 Market Square",
    "city": "Atlanta",
    "state": "GA",
    "countryLetterCode": "US",
    "postalCode": "31772"
  },
  "phoneNumber": "",
  "email": "jim.glynn@cronuscorp.net",
  "website": "",
  "taxLiable": true,
  "currencyCode": "USD",
  "paymentTerms": {
    "code": "1M(8D)",
    "description": "1 Month/2% 8 days"
  },
  "shipmentMethod": null,
  "paymentMethod": {
    "code": "BANK",
    "description": "Bank Transfer"
  },
  "blocked": " ",
  "balance": 0,
  "lastModifiedDateTime": "2017-03-07T00:35:28.983Z"
}
```

## See Also
[Microsoft Graph Reference](../api/dynamics_graph_reference.md)  
