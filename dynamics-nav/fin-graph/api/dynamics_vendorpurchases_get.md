---
title: Get vendorPurchases | Microsoft Docs
description: Gets a vendor purchase object in Dynamics 365 for Financials. 
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

# Get vendorPurchases
Retrieve the properties and relationships of a vendor purchases report object for Dynamics 365 for Financials.

## HTTP request
```
GET /financials/companies({id})/vendorPurchases
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and vendorPurchases object in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://api.financials.dynamics.com/v1.0/api/beta/companies({id})/vendorPurchases
```

**Response**

Here is an example of the response. 

> [!NOTE]  
>   The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
  "vendorId": "id-value",
  "vendorNumber": "10000",
  "name": "Fabrikam, Inc.",
  "totalPurchaseAmount": 21632.25,
  "dateFilter_FilterOnly": null
}
```


## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 