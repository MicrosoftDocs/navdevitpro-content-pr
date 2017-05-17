---
title: CREATE vendor method | Microsoft Docs
description: Creates a vendor.
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

# Create vendor
Create a vendor in Dynamics 365 for Financials.

## HTTP request
```
POST /financials/companies/{id}/vendors
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer. Required. |
|Content-Type  |application/json   |

## Request body
In the request body, supply a JSON representation of vendors object.

## Response
If successful, this method returns ```201 Created``` response code and vendors object in the response body.

## Example

**Request**

Here is an example of a request.

```json
POST https://graph.microsoft.com/beta/financials/companies/{id}/vendors
Content-type: application/json

{
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
  "number": "40000",
  "displayName": "Wide World Importers",
  "lastModifiedDateTime": "2015-11-09T02:14:32Z"
}

```

## See also
[Microsoft Graph Reference](../api/dynamics_graph_reference.md)  
