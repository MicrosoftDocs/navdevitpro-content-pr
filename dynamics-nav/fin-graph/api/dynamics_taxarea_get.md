---
title: Get taxAreas | Microsoft Docs
description: Gets a tax area object in Dynamics 365 for Financials. 
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

# Get taxAreas
Retrieve the properties and relationships of a tax area object for Dynamics 365 for Financials.

## HTTP request

```
GET /financials/companies/({id})/taxAreas/({id})
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and tax area object in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://api.financials.dynamics.com/v1.0/api/beta/companies/({id})/taxAreas/({id})
```

**Response**

Here is an example of the response. 

> [!NOTE]  
>   The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
  "id": "id-value",
  "code": "28012001T",
  "displayName": "tax area",
  "lastModifiedDateTime": "2017-05-17T11:30:01.313Z"
}
```

## See also
[Microsoft Graph Reference](../api/dynamics_graph_reference.md)  
