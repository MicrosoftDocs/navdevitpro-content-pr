---
title: CREATE customer method | Microsoft Docs
description: Creates a customer.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/16/2017
ms.author: solsen
---

# POST Customer Method
Create a customer in Dynamics 365 for Financials.

## HTTP request
```
POST /financials/companies/{id}/customers
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer. Required.  |
|Content-Type  |application/json  |

## Request body
In the request body, supply a JSON representation of customers object.

## Response
If successful, this method returns ```201 Created``` response code and customers object in the response body.

## Example

**Request**

Here is an example of a request.

```json
POST https://graph.microsoft.com/beta/finacials/companies/{id}/customers
Content-type: application/json

{
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
  "blocked": " "
}

```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
HTTP/1.1 201 Created
Content-type: application/json

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
