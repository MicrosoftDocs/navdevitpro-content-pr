---
title: CREATE itemCategories method | Microsoft Docs
description: Creates an itemCategory.
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

# CREATE itemCategories Method
Create an itemCategory in Dynamics 365 Financials.

## Prerequisites

## HTTP request
```
POST /financials/companies/{id}/itemCategories
```
## Optional query parameters

## Request headers

|Header|Value|
|------|-----|
|Authorization  |Bearer. Required.    |
|Content-Type  |application/json    |

## Request body

In the request body, supply a JSON representation of itemCategories object.

## Reponse

If successful, this method returns 201, Created response code and itemCategories object in the response body.

## Example

**Request**

Here is an example of a request.

```
POST https://graph.microsoft.com/beta/finacials/companies/{id}/itemCategories
Content-type: application/json

{
  "code": "CHAIR",
  "displayName": "Office Chair"
}
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```
HTTP/1.1 201 Created
Content-type: application/json

{
  "id": "id-value",
  "code": "CHAIR",
  "displayName": "Office Chair",
  "lastModifiedDateTime": "2017-03-15T02:21:24.047Z"
}

```



## See Also
[Microsoft Graph Reference](graph-reference.md)  