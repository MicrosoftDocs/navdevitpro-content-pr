---
title: GET CashFlowStatement method | Microsoft Docs
description: Gets a CashFlowStatement.
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

# Get cash flow statement
Retrieve the properties and relationships of a cash flow statement report object for Dynamics 365 for Financials.

## HTTP request
```
GET /financials/companies/{id}/cashFlowStatement
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and cashFlowStatement object in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://api.financials.dynamics.com/v1.0/api/beta/companies/{id}/cashFlowStatement?$orderby=lineNumber&$filter=dateFilter ge 2019-01-01 and dateFilter le 2020-12-31
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
  "lineNumber": 90000,
  "display": "Net Cash Provided by Operating Activities",
  "netChange": 39133.89,
  "lineType": "total",
  "indentation": 1,
  "dateFilter": "2016-12-31"    
}
```


## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 