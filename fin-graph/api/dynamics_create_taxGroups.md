---
title: CREATE Tax Groups method | Microsoft Docs
description: Creates a Tax Group.
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

# POST Tax Groups Method
Create a taxGroups in Dynamics 365 for Financials.

## HTTP request
```
POST /financials/companies/{id}/taxGroups
```
## Optional query parameters

## Request headers

|Header|Value|
|------|-----|
|Authorization  |Bearer. Required. |
|Content-Type  |application/json   |

## Request body
In the request body, supply a JSON representation of taxGroups object.

## Response
If successful, this method returns ```201 Created``` response code and taxGroups object in the response body.

## Example

**Request**

Here is an example of a request.

```json
POST https://graph.microsoft.com/beta/financials/companies/{id}/taxGroups
Content-type: application/json

{
  "code": "FURNITURE",
  "displayName": "Taxable Olympic Furniture"  
}
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
HTTP/1.1 201 Created
Content-type: application/json

{
  "id": "id-value",
  "code": "FURNITURE",
  "displayName": "Taxable Olympic Furniture",
  "lastModifiedDateTime": "2017-03-15T02:20:57.09Z"
}

```



## See Also
[Microsoft Graph Reference](../api/dynamics_graph_reference.md)  