---
title: Create dimensionLines | Microsoft Docs
description: Creates a dimension line in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/01/2019
ms.author: solsen
---

# Create dimensionLines
Create a dimension line object in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request

```
POST /businesscentral/companies({id})/dimensionLines
```

## Request headers

|Header        |Value                    |
|--------------|-------------------------|
|Authorization |Bearer {token}. Required.|
|Content-Type  |application/json         |

## Request body
In the request body, supply a JSON representation of a **dimensionLines** object.

## Response
If successful, this method returns ```201 Created``` response code and a **dimensionLines** object in the response body.

## Example

**Request**

Here is an example of a request.

```json
POST https://api.businesscentral.dynamics.com/v1.0/api/v1.0/companies({id})/dimensionLines
Content-type: application/json

{
  "parentId" : "parentId-value",
  "id" : "id-value",
  "code" : "DEPARTMENT",
  "valueId" : "valueId-value",
  "valueCode" : "SALES"
}
```
**Response**

```json
HTTP/1.1 201 Created
Content-type: application/json

{
  "parentId" : "parentId-value",
  "id" : "id-value",
  "code" : "DEPARTMENT",
  "displayName": "Department",
  "valueId" : "valueId-value",
  "valueCode" : "SALES",
  "valueDisplayName": "Production"
}
```

## See also
  
[Dimension Line](../resources/dynamics_dimensionline.md)  
[Get Dimension Line](../api/dynamics_dimensionline_get.md)  
[Patch Dimension Line](../api/dynamics_dimensionline_update.md)  
[Delete Dimension Line](../api/dynamics_dimensionline_delete.md)  