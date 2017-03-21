---
title: GET account method | Microsoft Docs
description: Gets an account.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/17/2017
ms.author: solsen
---

# GET Account Method
Retrieve the properties and relationships of an account object for [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].


## HTTP request
```
GET /financials/companies/{id}/accounts/{id}
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer. Required. |

## Request body
Do not supply a request body for this method.

## Reponse
If successful, this method returns a ```200 OK``` response code and accounts object in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://graph.microsoft.com/beta/financials/companies/{id}/accounts/{id}
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
    "id": "id-value",
    "number": "10700",
    "displayName": "Inventory",
    "category": "Assets",
    "subCategory": "Inventory",
    "blocked": false,
    "lastModifiedDateTime": "2017-03-15T02:20:58.747Z"
}
```


## See Also
[Microsoft Graph Reference](graph-reference.md)  
