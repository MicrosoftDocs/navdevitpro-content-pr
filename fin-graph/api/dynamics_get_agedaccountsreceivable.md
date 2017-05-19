---
title: GET AgedAccountsReceivable method | Microsoft Docs
description: Gets a AgedAccountsReceivable.
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

# Get aged accounts receivable
Retrieve the properties and relationships of a AgedAccountsReceivable report object for Dynamics 365 for Financials.

## HTTP request
```
GET /financials/companies/{id}/agedAccountsReceivable
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and agedAccountsReceivable object in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://graph.microsoft.com/beta/financials/companies/{id}/agedAccountsReceivable
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
  "customerId": "id-value",
  "customerNumber": "30000",
  "name": "Relecloud",
  "currencyCode": "USD",
  "before": 0,
  "period1": 349615.45,
  "period2": 0,
  "period3": 0,
  "after": 0,
  "balance": 349615.45,
  "periodStartDateFilter": "2017-04-25",
  "periodLengthFilter": "3M"   
}
```


## See also
[Working with Dynamics 365 for Finance and Operations, Business Edition in Microsoft Graph](../resources/dynamics_overview.md) 