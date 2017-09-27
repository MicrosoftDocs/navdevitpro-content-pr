---
title: Create taxGroups | Microsoft Docs
description: Creates a tax group object in Dynamics 365 for Financials. 
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

# Create taxGroups
Create a taxGroups object in Dynamics 365 for Financials.

## HTTP request
```
POST /financials/companies/({id})/taxGroups
```

## Request headers

|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |
|Content-Type  |application/json   |

## Request body
In the request body, supply a JSON representation of taxGroups object.

## Response
If successful, this method returns ```201 Created``` response code and taxGroups object in the response body.

## Example

**Request**

Here is an example of a request.

```json
POST https://api.financials.dynamics.com/v1.0/api/beta/companies/({id})/taxGroups
Content-type: application/json

{
  "code": "FURNITURE",
  "displayName": "Taxable Olympic Furniture"  
}
```

**Response**

Here is an example of the response. 

> [!NOTE]  
>   The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

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
[Working with Dynamics 365 for Financials in Microsoft Graph](../api/dynamics_graph_reference.md)  
