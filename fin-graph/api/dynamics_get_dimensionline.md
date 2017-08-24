---
title: GET dimensionLines method | Microsoft Docs
description: Gets a dimension lines.
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

# Get dimensionLines
Retrieve the properties and relationships of a dimension line object for Dynamics 365 for Financials.

## Prerequisites

## HTTP request

```
If you want to receive all of the dimension lines of a specific parent entity, you can do it with the following URL:
GET /financials/companies/{id}/dimensionLines?$filter=parentId eq {id}

In order to get a specific dimension line you can use the following URL:
GET /financials/companies/{id}/dimensionLines(parentId={id},id={id})

```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and a dimension line object in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://api.financials.dynamics.com/v1.0/api/beta/companies/{id}/dimensionLines(parentId={id},id={id})
```

**Response**

Here is an example of the response. 

> [!NOTE]  
>   The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

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

## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 
