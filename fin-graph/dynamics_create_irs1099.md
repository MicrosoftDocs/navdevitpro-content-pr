---
title: CREATE IRS 1099 Code Method | Microsoft Docs
description: Creates a IRS 1099 Code.
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

# POST IRS 1099 Code Method
Create a irs1099Codes in [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].

## HTTP request
```
POST /financials/companies/{id}/irs1099Codes
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer. Required.    |
|Content-Type  |application/json    |

## Request body
In the request body, supply a JSON representation of irs1099Codes object.

## Response
If successful, this method returns ```201 Created``` response code and irs1099Codes object in the response body.

## Example

**Request**

Here is an example of a request.

```json
POST https://graph.microsoft.com/beta/finacials/companies/{id}/irs1099Codes
Content-type: application/json

{
  "code": "R-10",
  "displayName": "State income tax withheld",
  "minimumReportable": 0
}
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
HTTP/1.1 201 Created
Content-type: application/json

{
  "id": "id-value",
  "code": "R-10",
  "displayName": "State income tax withheld",
  "minimumReportable": 0,
  "lastModifiedDateTime": "0001-01-01T00:00:00Z"
}

```



## See Also
[Microsoft Graph Reference](dynamics_graph_reference.md)  