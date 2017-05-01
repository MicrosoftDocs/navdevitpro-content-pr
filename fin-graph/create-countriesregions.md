---
title: CREATE Countries/Regions method | Microsoft Docs
description: Creates a Countries/Regions.
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

# POST Countries/Regions Method
Create a countriesRegions in [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].

## HTTP request
```
POST /financials/companies/{id}/countriesRegions
```
## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer. Required. |
|Content-Type  |application/json   |

## Request body
In the request body, supply a JSON representation of countriesRegions object.

## Response
If successful, this method returns ```201 Created``` response code and countriesRegions object in the response body.

## Example

**Request**

Here is an example of a request.

```json
POST https://graph.microsoft.com/beta/finacials/companies/{id}/countriesRegions
Content-type: application/json

{
  "code": "US",
  "displayName": "USA",
  "addressFormat": "City+County+Post Code"
}
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
HTTP/1.1 201 Created
Content-type: application/json

{
  "id": "id-value",
  "code": "US",
  "displayName": "USA",
  "addressFormat": "City+County+Post Code",
  "lastModifiedDateTime": "2017-03-14T15:22:31.753Z"
}

```

## See Also
[Microsoft Graph Reference](graph-reference.md)  