---
title: Create taxAreas | Microsoft Docs
description: Creates a tax area object in Dynamics for Financials. 
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

# Create taxAreas
Creates a tax area object in Dynamics 365 for Financials.

## HTTP request

```
POST /financials/companies({id})/taxAreas({id})
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required.    |
|Content-Type  |application/json    |

## Request body
In the request body, supply a JSON representation of a **taxAreas** object.

## Response
If successful, this method returns ```201 Created``` response code and a **taxAreas** object in the response body.

## Example

**Request**

Here is an example of a request.

```json
POST https://api.financials.dynamics.com/v1.0/api/beta/companies({id})/taxAreas
Content-type: application/json

```json
{
  "code": "44442001T"
}
```

**Response**

```json
HTTP/1.1 201 Created
Content-type: application/json

{
  "id": "id-value",
  "code": "44442001T",
  "displayName": "tax area",
  "lastModifiedDateTime": "2017-05-17T11:30:01.313Z"
}
```

## See also
[Microsoft Graph Reference](../api/dynamics_graph_reference.md)  
