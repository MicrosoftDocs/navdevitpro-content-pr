---
title: GET Dimension Line method | Microsoft Docs
description: Gets a dimension line.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/08/2017
ms.author: solsen
---

# GET Dimension Line Method
Retrieve the properties and relationships of a dimension line object for [!INCLUDE[d365fin_long_md](../includes/d365fin_long_md.md)].

## Prerequisites

## HTTP request

```
GET /financials/companies/{id}/{ParentEntity}/{id}/dimensionLines(parentId={id},id={id})
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and a dimension line object in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://graph.microsoft.com/beta/financials/companies/{id}/{ParentEntity}/{id}/dimensionLines(parentId={id},id={id})
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
  "parentId": "id-value",
  "id": "id-value",
  "code": "DEPARTMENT",
  "displayName": "Department",
  "valueId": "id-value",
  "valueCode": "SALES",
  "valueDisplayName": "Sales"
}
```

## See Also
[Microsoft Graph Reference](../api/dynamics_graph_reference.md)  
