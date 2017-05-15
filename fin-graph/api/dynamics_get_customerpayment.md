---
title: GET customer payment method | Microsoft Docs
description: Gets a customer payment.
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

# GET Customer Payment Method
Retrieve the properties and relationships of a customerPayments object for Dynamics 365 for Financials.

## HTTP request

```
GET /financials/companies/{id}/customerPayments/{id}
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and customerPayments object in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://graph.microsoft.com/beta/financials/companies/{id}/customerPayments/{id}
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
  "id": "id-value",
  "lineNumber": 10000,
  "customerId": "customerId-value",
  "customerNumber": "10400",
  "postingDate": "2015-12-31",
  "documentNumber": "1234",
  "externalDocumentNumber": "",
  "amount": 1500,
  "appliesToInvoiceId": "appliesToInvoiceId-value",
  "appliesToInvoiceNumber": "100000",
  "description": "",
  "comment": "",
  "financialDimension1": "PROD",
  "financialDimension1": "SW",
  "lastModifiedDateTime": "2017-03-17T19:02:22.043Z"
}
```

## See Also
[Microsoft Graph Reference](../api/dynamics_graph_reference.md)  
