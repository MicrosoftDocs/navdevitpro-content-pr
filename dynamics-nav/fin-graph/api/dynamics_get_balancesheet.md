---
title: GET BalanceSheet method | Microsoft Docs
description: Gets a BalanceSheet.
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

# Get balance sheet
Retrieve the properties and relationships of a balance sheet report object for Dynamics 365 for Financials.

## HTTP request
```
GET /financials/companies/{id}/balanceSheet
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and balanceSheet object in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://api.financials.dynamics.com/v1.0/api/beta/companies/{id}/balanceSheet?$orderby=lineNumber&$filter=dateFilter eq 2020-12-30
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
  "lineNumber": 10000,
  "display": "Assets",
  "balance": 11860.69,
  "lineType": "header",
  "indentation": 0,
  "dateFilter": "2020-12-30"
}
```


## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 