---
title: GET IRS 1099 Code method | Microsoft Docs
description: Gets a IRS 1099 Code.
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

# Get IRS 1099 code
Retrieve the properties and relationships of a irs1099Codes object for Dynamics 365 for Financials.

## HTTP request

```
GET /financials/companies/{id}/irs1099Codes/{id}
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and irs1099Codes object in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://graph.microsoft.com/beta/financials/companies/{id}/irs1099Codes/{id}
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
  "id": "id-value",
  "code": "R-10",
  "displayName": "State income tax withheld",
  "minimumReportable": 0,
  "lastModifiedDateTime": "0001-01-01T00:00:00Z"
}
```


## See Also
[Microsoft Graph Reference](../api/dynamics_graph_reference.md)  