---
title: UPDATE Tax Groups method | Microsoft Docs
description: Updates a Tax Group.
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

# Update tax groups
Update the properties of a taxGroups object for Dynamics 365 for Financials.

## HTTP request
```
PATCH /financials/companies/{id}/taxGroups/{id}
```

## Request headers
|Header|Value|
|------|-----|
|Authorization |Bearer. Required.|
|Content-Type  |application/json|
|If-Match      |Required. When this request header is included and the eTag provided does not match the current tag on the taxGroups, the taxGroups will not be updated. |

## Request body
In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

## Response
If successful, this method returns a ```200 OK``` response code and an updated taxGroups object in the response body.

## Example

**Request**

Here is an example of the request.
```json
PATCH https://graph.microsoft.com/beta/financials/companies/{id}/taxGroups{id}
Content-type: application/json

{
  "displayName": "Taxable Furniture"
}
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
HTTP/1.1 200 OK
Content-type: application/json

{
  "id": "id-value",
  "code": "FURNITURE",
  "displayName": "Taxable Furniture",
  "lastModifiedDateTime": "2017-03-15T02:20:57.09Z"
  }
```


## See Also
[Working with Dynamics 365 for Financials in Microsoft Graph](../api/dynamics_graph_reference.md)  
