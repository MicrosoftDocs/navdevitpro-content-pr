---
title: GET CustomerSales method | Microsoft Docs
description: Gets a CustomerSales.
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

# GET Customer Sales Method
Retrieve the properties and relationships of a customerSales report object for [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].

## HTTP request
```
GET /financials/companies/{id}/customerSales
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and customerSales object in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://graph.microsoft.com/beta/financials/companies/{id}/customerSales
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
  "customerId": "id-value",
  "customerNumber": "50000",
  "name": "Relecloud",
  "totalSalesAmount": 83956.45,
  "dateFilter_FilterOnly": null  
}
```


## See Also
[Microsoft Graph Reference](dynamics_graph_reference.md)  