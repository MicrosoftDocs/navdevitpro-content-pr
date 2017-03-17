---
title: GET itemCategories method | Microsoft Docs
description: Gets an itemCategory.
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

# GET itemCategories Method

Retrieve the properties and relationships of an itemCategories object.

## Prerequisites

## HTTP request

An itemCategory from Dynamics 365 Financials.

```
GET /financials/companies/{id}/itemCategories/{id}
```
## Optional query parameters

## Request headers

|Header|Value|
|------|-----|
|Authorization  |Bearer . Required. |

## Request body

Do not supply a request body for this method.

## Reponse

If successful, this method returns a 200 OK response code and itemCategories object in the response body.

## Example

**Request**

Here is an example of the request.
```
GET https://graph.microsoft.com/beta/financials/companies/{id}/itemCategories/{id}
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```
{
  "id": "id-value",
  "code": "CHAIR",
  "displayName": "Office Chair",
  "lastModifiedDateTime": "2017-03-15T02:21:24.047Z"
```


## See Also
[Microsoft Graph Reference](graph-reference.md)  