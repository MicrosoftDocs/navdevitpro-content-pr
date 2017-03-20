---
title: CREATE paymentTerms Method | Microsoft Docs
description: Creates a paymentTerms.
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

# CREATE paymentTerms Method
Create a paymentTerms in Dynamics 365 Financials.

## Prerequisites

## HTTP request
```
POST /financials/companies/{id}/paymentTerms
```
## Optional query parameters

## Request headers

|Header|Value|
|------|-----|
|Authorization  |Bearer. Required.    |
|Content-Type  |application/json    |

## Request body

In the request body, supply a JSON representation of paymentTerms object.

## Reponse

If successful, this method returns 201, Created response code and paymentTerms object in the response body.

## Example

**Request**

Here is an example of a request.

```
POST https://graph.microsoft.com/beta/finacials/companies/{id}/paymentTerms
Content-type: application/json

{
  "code": "7 DAYS",
  "displayName": "Net 7 days",
  "dueDateCalculation": "7D",
  "discountDateCalculation": "",
  "discountPercent": 0,
  "calculateDiscountOnCreditMemos": false
}
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```
HTTP/1.1 201 Created
Content-type: application/json

{
  "id": "id-value",
  "code": "7 DAYS",
  "displayName": "Net 7 days",
  "dueDateCalculation": "7D",
  "discountDateCalculation": "",
  "discountPercent": 0,
  "calculateDiscountOnCreditMemos": false,
  "lastModifiedDateTime": "2017-03-03T02:14:32Z"
}

```



## See Also
[Microsoft Graph Reference](graph-reference.md)  