---
title: CREATE journal line method | Microsoft Docs
description: Creates a journal line.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/21/2017
ms.author: solsen
---

# POST Journal Line Method
Creates a journal line in [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].

## HTTP request
```
POST /financials/companies/{id}/journalLines/{id}
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer. Required.    |
|Content-Type  |application/json    |

## Request body
In the request body, supply a JSON representation of journalLine object.

## Response
If successful, this method returns ```201 Created``` response code and journalLine object in the response body.

## Example

**Request**

Here is an example of a request.

```json
POST https://graph.microsoft.com/beta/finacials/companies/{id}/journalLine
Content-type: application/json

```
**Response**
```

## See Also
[Microsoft Graph Reference](graph-reference.md)  
