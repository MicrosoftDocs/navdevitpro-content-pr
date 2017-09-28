--- 
title: Get agedAccountsReceivable | Microsoft Docs
description: Gets an aged accounts receivable report object in Dynamics 365 for Financials.
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

# Get agedAccountsReceivable
Retrieve the properties and relationships of an aged accounts receivable report object for Dynamics 365 for Financials.

## HTTP request
```
GET /financials/companies/({id})/agedAccountsReceivable
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and agedAccountsReceivable object in the response body.

## Example

**Request**

Here is an example of the request.

```json
GET https://api.financials.dynamics.com/v1.0/api/beta/companies/({id})/agedAccountsReceivable
```

**Response**

Here is an example of the response. 

> [!NOTE]  
>   The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
  "customerId": "id-value",
  "customerNumber": "30000",
  "name": "Relecloud",
  "currencyCode": "USD",
  "balanceDue": 349615.45,
  "currentAmount": 0,
  "period1Amount": 349615.45,
  "period2Amount": 0,
  "period3Amount": 0,
  "agedAsOfDate": "2017-04-25",
  "periodLengthFilter": "3M"   
}
```


## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 
