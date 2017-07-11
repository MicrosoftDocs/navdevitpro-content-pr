---
title: GET RetainedEarningsStatement method | Microsoft Docs
description: Gets a RetainedEarningsStatement.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/11/2017
ms.author: solsen
---

# Get retained earnings statement
Retrieve the properties and relationships of a retained earnings statement report object for Dynamics 365 for Financials.

## HTTP request
```
GET /financials/companies/{id}/retainedEarningsStatement
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and retainedEarningsStatement object in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://graph.microsoft.com/beta/financials/companies/{id}/retainedEarningsStatement?$orderby=lineNumber&$filter=dateFilter ge 2019-01-01 and dateFilter le 2020-12-31
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
  "lineNumber": 20000,
  "display": "Net Income",
  "netChange": 77770.94,
  "lineType": "detail",
  "indentation": 0,
  "dateFilter": "2016-12-31"   
}
```


## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 