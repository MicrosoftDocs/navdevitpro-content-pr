---
title: GET AgedAccountsPayable method | Microsoft Docs
description: Gets a AgedAccountsPayable.
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

# Get aged accounts payable
Retrieve the properties and relationships of an aged accounts payable report object for Dynamics 365 for Financials.

## HTTP request
```
GET /financials/companies/{id}/agedAccountsPayable
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and agedAccountsPayable object in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://api.financials.dynamics.com/v1.0/api/beta/companies/{id}/agedAccountsPayable
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
  "vendorId": "id-value",
  "vendorNumber": "50000",
  "name": "Nod Publishers",
  "currencyCode": "USD",
  "before": 0,
  "period1": 0,
  "period2": 0,
  "period3": 0,
  "after": 17273.87,
  "balance": 17273.87,
  "periodStartDateFilter": "2019-01-01",
  "periodLengthFilter": "3M"  
}
```


## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 