---
title: Create journals | Microsoft Docs
description: Creates a journal object in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/01/2019
ms.author: solsen
---

# Create journals
Creates a journal in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)]. 

## HTTP request
Replace the URL prefix for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] depending on environment following the [guideline](../../v1.0/endpoints-apis-for-dynamics.md).

```
POST businesscentralPrefix/companies({id})/journals({id})
```

## Request headers

|Header        |Value                     |
|--------------|--------------------------|
|Authorization |Bearer {token}. Required. |
|Content-Type  |application/json          |

## Request body
In the request body, supply a JSON representation of a **journals** object.

## Response
If successful, this method returns ```201 Created``` response code and a **journals** object in the response body.

## Example

**Request**

Here is an example of a request.

```json
POST https://{businesscentralPrefix}/api/v1.0/companies({id})/journals
Content-type: application/json
```json
{
  "code": "DEFAULT"
}
```

**Response**

```json
HTTP/1.1 201 Created
Content-type: application/json

{
  "id": "id-value",
  "code": "DEFAULT",
  "displayName": "Default Journal Batch",
  "lastModifiedDateTime": "2017-05-17T11:30:01.313Z"
}
```

## See also
[Graph Reference](../api/dynamics_graph_reference.md)  
  
[Journal](../resources/dynamics_journal.md)  
[Get Journal](../api/dynamics_journal_get.md)  
[Update Journal](../api/dynamics_journal_update.md)  
[Delete Journal](../api/dynamics_journal_delete.md)  