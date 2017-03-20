---
title: UPDATE paymentTerms method | Microsoft Docs
description: Updates a paymentTerms.
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

# UPDATE paymentTerms Method

Update the properties of a paymentTerms object.

## Prerequisites

## HTTP request
A paymentTerms from Dynamics 365 Financials.

```
PATCH /financials/companies/{id}/paymentTerms/{id}
```
## Optional query parameters

## Request headers

|Header|Value|
|------|-----|
|Authorization|Bearer . Required.|
|Content-Type|application/json|
|If-Match   |Required. When this request header is included and the eTag provided does not match the current tag on the paymentTerms, the paymentTerms will not be updated. |

## Request body

In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

## Response

If successful, this method returns a 200 OK response code and an updated paymentTerms object in the response body.

## Example

**Request**

Here is an example of the request.
```
PATCH https://graph.microsoft.com/beta/financials/companies/{id}/paymentTerms{id}
Content-type: application/json

{
  "displayName": "Net 7 days with Discount",
  "discountPercent": 10
}
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```
HTTP/1.1 200 OK
Content-type: application/json

{
  "id": "id-value",
  "code": "7 DAYS",
  "displayName": "Net 7 days with Discount",
  "dueDateCalculation": "7D",
  "discountDateCalculation": "",
  "discountPercent": 10,
  "calculateDiscountOnCreditMemos": false,
  "lastModifiedDateTime": "2017-03-15T02:20:55.203Z"
}
```


## See Also
[Microsoft Graph Reference](graph-reference.md)  