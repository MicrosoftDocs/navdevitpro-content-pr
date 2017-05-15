---
title: GET journal line method | Microsoft Docs
description: Gets a journal line.
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

# GET Journal Line Method
Retrieve the properties and relationships of a journalLines object for Dynamics 365 for Financials.

## HTTP request

```
GET /financials/companies/{id}/journalLines/{id}
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and journalLines object in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://graph.microsoft.com/beta/financials/companies/{id}/journalLines/{id}
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
  "id": "id-value",
  "lineNumber": 10000,
  "accountId": "id-value",
  "accountNumber": "10400",
  "postingDate": "2015-12-31",
  "documentNumber": "1234",
  "externalDocumentNumber": "",
  "amount": 1500,
  "description": "Accounts Receivable",
  "comment": "",
  "financialDimension1": "PROD",
  "financialDimension1": "SW",
  "lastModifiedDateTime": "2017-03-17T19:02:22.043Z"
}
```

## See Also
[Microsoft Graph Reference](../api/dynamics_graph_reference.md)  
