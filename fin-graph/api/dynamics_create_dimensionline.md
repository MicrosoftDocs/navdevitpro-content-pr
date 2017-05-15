---
title: CREATE Dimension Line method | Microsoft Docs
description: Creates a dimension line.
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

# POST Dimension Line Method
Create a dimensionLine in [!INCLUDE[d365fin_long_md](../includes/d365fin_long_md.md)].

## HTTP request

```
POST /financials/companies/{id}/{ParentEntity}/{id}/dimensionLines
```

## Request headers

|Header|Value|
|------|-----|
|Authorization  |Bearer. Required.    |
|Content-Type  |application/json    |

## Request body
In the request body, supply a JSON representation of a dimensionLine object.

## Response
If successful, this method returns ```201 Created``` response code and a dimensionLine object in the response body.

## Example

**Request**

Here is an example of a request.

```json
POST https://graph.microsoft.com/beta//financials/companies/{id}/{ParentEntity}/{id}/dimensionLines
Content-type: application/json

{
  "id" : "id-value",
  "code" : "DEPARTMENT",
  "valueId" : "id-value",
  "valueCode" : "SALES"
}

## See Also
[Microsoft Graph Reference](../api/dynamics_graph_reference.md)