---
title: CREATE Sales Order Line method | Microsoft Docs
description: Creates a sales order line.
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

# POST Sales Order Line Method
Create a salesOrder in Dynamics 365 for Financials.

## HTTP request

```
POST /financials/companies/{id}/salesOrders/{id}/salesOrderLines
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
POST https://graph.microsoft.com/beta/financials/companies/{id}/salesOrders/{id}/salesOrderLines
Content-type: application/json

{
"itemId": "id-value",
"lineType": "Item",
"quantity": 9
}

## See Also
[Microsoft Graph Reference](../api/dynamics_graph_reference.md)