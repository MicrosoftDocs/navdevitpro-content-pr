---
title: CREATE Sales Order method | Microsoft Docs
description: Creates a sales order.
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

# POST Sales Order Method
Create a salesOrder in Dynamics 365 for Financials.

## HTTP request

```
POST /financials/companies/{id}/salesOrders
```

## Request headers

|Header|Value|
|------|-----|
|Authorization  |Bearer. Required.    |
|Content-Type  |application/json    |

## Request body
In the request body, supply a JSON representation of a salesOrder object.

## Response
If successful, this method returns ```201 Created``` response code and a salesOrder object in the response body.

## Example

**Request**

Here is an example of a request.

```json
POST https://graph.microsoft.com/beta/financials/companies/{id}/salesOrders
Content-type: application/json

{
  "id": "id-value",
  "number": "1009",
  "orderDate": "2015-12-31",
  "customerNumber": "GL00000008",
  "currencyCode": "GBP",
  "paymentTerms": "COD"
}

## See Also
[Microsoft Graph Reference](../api/dynamics_graph_reference.md)  