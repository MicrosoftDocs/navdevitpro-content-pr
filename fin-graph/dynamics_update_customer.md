---
title: UPDATE customer method | Microsoft Docs
description: Updates a customer.
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

# PATCH Customer Method
Update the properties of a customers object for [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].


## HTTP request

```
PATCH /financials/companies/{id}/customers/{id}
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer. Required. |
|Content-Type   |application/json. |
|If-Match       |Required. When this request header is included and the eTag provided does not match the current tag on the customer, the customer will not be updated. |

## Request body
In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

## Response
If successful, this method returns a ```200 OK``` response code and an updated customers object in the response body.

## Example

**Request**

Here is an example of the request.

```json
PATCH https://graph.microsoft.com/beta/financials/companies/{id}/customers{id}
Content-type: application/json

{
  "displayName": "Coho Winery Inc.",
  "phoneNumber": "(555) 555-1234"
}
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
HTTP/1.1 200 OK
Content-type: application/json

{
  "id": "id-value",
  "number": "10000",
  "displayName": "Coho Winery Inc.",
  "address": {
    "street": "192 Market Square",
    "city": "Atlanta",
    "state": "GA",
    "countryLetterCode": "US",
    "postalCode": "31772"
  },
  "phoneNumber": "(555) 555-1234",
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
[Microsoft Graph Reference](dynamics_graph_reference.md)  
