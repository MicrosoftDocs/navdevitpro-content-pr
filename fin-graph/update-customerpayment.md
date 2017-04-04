---
title: UPDATE customer payments method | Microsoft Docs
description: Updates a customer payments.
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

# PATCH Customer Payments Method
Update the properties of a customerPayments object for [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].

## HTTP request

```
PATCH /financials/companies/{id}/customerPayments/{id}
```

## Request headers
|Header|Value|
|------|-----|
|Authorization |Bearer. Required.|
|Content-Type  |application/json|
|If-Match      |Required. When this request header is included and the eTag provided does not match the current tag on the customerPayments, the customerPayments will not be updated. |

## Request body
In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

## Response
If successful, this method returns a ```200 OK``` response code and an updated customerPayments object in the response body.

## Example

**Request**

Here is an example of the request.
```json
PATCH https://graph.microsoft.com/beta/financials/companies/{id}/customerPayments{id}
Content-type: application/json

{
  "amount": 2000
}
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
HTTP/1.1 200 OK
Content-type: application/json

{
  "id": "id-value",
  "lineNumber": 10000,
  "customerId": "",
  "customerNumber": "",
  "postingDate": "2015-12-31",
  "documentNumber": "D00001",
  "externalDocumentNumber": "",
  "amount": -2000,
  "appliesToInvoiceId": "appliesToInvoiceId-value",
  "appliesToInvoiceNumber": "100000",
  "description": "",
  "comment": "",
  "financialDimension1": "",
  "financialDimension1": "",
  "lastModifiedDateTime": "2017-03-17T19:02:22.043Z"
}
```
## See Also
[Microsoft Graph Reference](graph-reference.md)  
