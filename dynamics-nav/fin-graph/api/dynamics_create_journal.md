---
title: Create journals | Microsoft Docs
description: Creates a journal object in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.prod: dynamics-nav-2018
ms.topic: reference
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/19/2018
ms.author: solsen
ROBOTS: NOINDEX
---

# Create journals
Creates a journal in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)]. 

## HTTP request
Replace the URL prefix for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] depending on environment following the [guideline](../../endpoints-apis-for-dynamics.md).

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
POST https://{businesscentralPrefix}/api/beta/companies({id})/journals
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
[Tips for working with the APIs](/dynamics365/business-central/dev-itpro/developer/devenv-connect-apps-tips)  
[Graph Reference](../api/dynamics_graph_reference.md)  
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Dynamics 365 Business Central](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[Journal](../resources/dynamics_journal.md)  
[Get Journal](../api/dynamics_journal_get.md)  
[Update Journal](../api/dynamics_journal_update.md)  
[Delete Journal](../api/dynamics_journal_delete.md)  
