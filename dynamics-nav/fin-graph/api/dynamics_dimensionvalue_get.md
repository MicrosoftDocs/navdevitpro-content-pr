---
title: Get dimensionValues | Microsoft Docs
description: Get a dimension value in Dynamics 365 for Financials.
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

# Get dimensionValues
Retrieve the properties and relationships of a dimension value object for Dynamics 365 for Financials.

## Prerequisites

## HTTP request

```
GET /financials/companies/({id})/dimensions/({id})/dimensionValues({id})
```

## Request headers
|Header       |Value                     |
|-------------|--------------------------|
|Authorization|Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and dimensionValue object in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://api.financials.dynamics.com/v1.0/api/beta/companies/({id})/dimensions/({id})/dimensionValues({id})
```

**Response**

Here is an example of the response. 

> [!NOTE]  
>   The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
  "id": "id-value",
  "code": "30",
  "displayName": "Europe North (EU)",
  "lastModifiedDateTime": "2017-03-17T19:02:22.043Z"
}
```

## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 
