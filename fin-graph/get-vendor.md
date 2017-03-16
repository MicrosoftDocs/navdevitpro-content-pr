---
title: GET Vendor method | Microsoft Docs
description: Gets a vendor.
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

# GET Vendor Method

Retrieve the properties and relationships of an vendors object.

## Prerequisites

## HTTP request

An vendor from Dynamics 365 Financials.

```
GET /financials/companies/{id}/vendors/{id}
```
## Optional query parameters

## Request headers

|Header|Value|
|------|-----|
|Authorization  |Bearer . Required. |

## Request body

Do not supply a request body for this method.

## Reponse

If successful, this method returns a 200 OK response code and vendors object in the response body.

## Example

**Request**

Here is an example of the request.
```
GET https://graph.microsoft.com/beta/financials/companies/{id}/vendors/{id}
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```
{
  "id": "8a487d16-7457-4bf9-903c-02d3d789400d",
  "number": "40000",
  "displayName": "Wide World Importers",
  "address": {
    "street": "51 Radcroft Road",
    "city": "Atlanta",
    "state": "GA",
    "countryLetterCode": "US",
    "postalCode": "31772"
  },
  "phoneNumber": "",
  "email": "toby.rhode@cronuscorp.net",
  "website": "",
  "taxRegistrationNumber": "",
  "currencyCode": "USD",
  "irs1099Code": "",
  "paymentTerms": {
    "code": "CM",
    "description": "Current Month"
  },
  "paymentMethod": {
    "code": "BANK",
    "description": "Bank Transfer"
  },
  "taxLiable": true,
  "blocked": " ",
  "balance": 0,
  "lastModifiedDateTime": "2017-03-07T00:35:29.667Z"
}
```


## See Also
[Microsoft Graph Reference](graph-reference.md)  
