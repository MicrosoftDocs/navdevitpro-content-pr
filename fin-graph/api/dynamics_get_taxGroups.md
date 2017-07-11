---
title: GET Tax Groups method | Microsoft Docs
description: Gets a Tax Group Method.
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

# Get tax groups
Retrieve the properties and relationships of a tax groups object for Dynamics 365 for Financials.

## HTTP request

```
GET /financials/companies/{id}/taxGroups/{id}
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and taxGroups object in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://graph.microsoft.com/beta/financials/companies/{id}/taxGroups/{id}
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
  "id": "id-value",
  "code": "FURNITURE",
  "displayName": "Taxable Olympic Furniture",
  "lastModifiedDateTime": "2017-03-15T02:20:57.09Z"
}
```


## See Also
[Working with Dynamics 365 for Financials in Microsoft Graph](../api/dynamics_graph_reference.md)  
