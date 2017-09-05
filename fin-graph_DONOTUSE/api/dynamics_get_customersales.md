---
title: GET CustomerSales method | Microsoft Docs
description: Gets a customer sales.
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

# Get customerSales
Retrieve the properties and relationships of a customer sales report object for Dynamics 365 for Financials.

## HTTP request
```
GET /financials/companies/({id})/customerSales
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and customerSales object in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://api.financials.dynamics.com/v1.0/api/beta/companies/({id})/customerSales
```

**Response**

Here is an example of the response. 

> [!NOTE]  
>   The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
  "customerId": "id-value",
  "customerNumber": "50000",
  "name": "Relecloud",
  "totalSalesAmount": 83956.45,
  "dateFilter_FilterOnly": null  
}
```


## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 