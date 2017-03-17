---
title: DELETE itemCategories method | Microsoft Docs
description: Deletes an itemCategory.
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

# DELETE itemCategories Method

Delete an itemCategory from Dynamics 365 Financials.

## Prerequisites

## HTTP request
```
DELETE /financials/companies/{id}/itemCategories/{id}
```
## Optional query parameters

## Request headers

|Header|Value|
|------|-----|
|Authorization  |Bearer . Required. |

## Request body

Do not supply a request body for this method.

## Response

If successful, this method returns 204, No Content response code. It does not return anything in the response body.

## Example

**Request**

Here is an example of the request.

```
DELETE https://graph.microsoft.com/beta/financials/companies/{id}/itemCategories/{id}
```

**Response** 

Here is an example of the response. 

```
HTTP/1.1 204 No Content
```

## See Also
[Microsoft Graph Reference](graph-reference.md)  