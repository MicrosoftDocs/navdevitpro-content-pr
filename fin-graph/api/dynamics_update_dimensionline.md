---
title: PATCH Dimension Line method | Microsoft Docs
description: Gets a dimension line.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/11/2017
ms.author: solsen
---

# Update cimension line
Update the properties of a dimension line object for Dynamics 365 for Financials.

## HTTP request

```
PATCH /financials/companies/{id}/dimensionLines(parentId={id},id={id})
```

## Request headers
|Header|Value|
|------|-----|
|Authorization |Bearer {token}. Required.|
|Content-Type  |application/json|
|If-Match      |Required. When this request header is included and the eTag provided does not match the current tag on the dimension line, the dimension line will not be updated. |

## Request body
In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

## Response
If successful, this method returns a ```200 OK``` response code and an updated dimension line object in the response body.

## Example

**Request**

Here is an example of the request.
```json
PATCH https://api.financials.dynamics.com/v1.0/api/beta/companies/{id}/dimensionLines(parentId={id},id={id})
Content-type: application/json

{
  "valueCode": "PROD"
}
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
HTTP/1.1 200 OK
Content-type: application/json

{
  "parentId": "id-value",
  "id": "id-value",
  "code": "DEPARTMENT",
  "displayName": "Department",
  "valueId": "id-value",
  "valueCode": "PROD",
  "valueDisplayName": "Production"
}
```

## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 
