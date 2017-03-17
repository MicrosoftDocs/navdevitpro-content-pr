---
title: UPDATE shipmentMethod method | Microsoft Docs
description: Updates a shipmentMethod.
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

# UPDATE shipmentMethods Method

Update the properties of a shipmentMethods object.

## Prerequisites

## HTTP request
A shipmentMethods from Dynamics 365 Financials.

```
PATCH /financials/companies/{id}/shipmentMethods/{id}
```
## Optional query parameters

## Request headers

|Header|Value|
|------|-----|
|Authorization|Bearer . Required.|
|Content-Type|application/json|
|If-Match   |Required. When this request header is included and the eTag provided does not match the current tag on the shipmentMethods, the shipmentMethods will not be updated. |

## Request body

In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

## Response

If successful, this method returns a 200 OK response code and an updated shipmentMethods object in the response body.

## Example

**Request**

Here is an example of the request.
```
PATCH https://graph.microsoft.com/beta/financials/companies/{id}/shipmentMethods{id}
Content-type: application/json

{
  "displayName": "Pickup at Store Location",
}
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```
HTTP/1.1 200 OK
Content-type: application/json

{
  "id": "id-value",
  "code": "PICKUP",
  "displayName": "Pickup at Store Location",
  "lastModifiedDateTime": "2017-03-15T02:20:57.09Z"
  }
```


## See Also
[Microsoft Graph Reference](graph-reference.md)  