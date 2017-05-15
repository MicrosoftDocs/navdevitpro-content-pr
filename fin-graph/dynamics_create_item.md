---
title: CREATE item method | Microsoft Docs
description: Creates an item.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/16/2017
ms.author: solsen
---

# POST Item Method
Create an item in [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)] for use on invoices, quotes, etc.

## HTTP request
```
POST /financials/companies/{id}/items
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer. Required.  |
|Content-Type |application/json |

## Request body
In the request body, supply a JSON representation of items object.

## Response
If successful, this method returns ```201 Created``` response code and items object in the response body.

## Example
**Request**

Here is an example of a request.

```json
POST https://graph.microsoft.com/beta/financials/companies/{id}/items
Content-type: application/json

{
  "number": "1896-S",
  "displayName": "ATHENS Desk",
  "type": "Inventory",
  "blocked": false,
  "baseUnitOfMeasure": {
    "unitCode": "PCS",
    "unitName": "Piece",
    "symbol": "",
    "unitConversion": null
  },
  "gtin": "",
  "itemCategory": {
    "categoryId": "TABLE", 
    "description": "Assorted Tables"
  },
  "inventory": 0,
  "unitPrice": 1000.8,
  "priceIncludesTax": false,
  "unitCost": 780.7,
  "taxGroupCode": "FURNITURE"
} 

```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
HTTP/1.1 201 Created
Content-type: application/json

{
  "id": "id-value",
  "number": "1896-S",
  "displayName": "ATHENS Desk",
  "lastModifiedDateTime": "2015-11-09T02:14:32Z"
}
```

## See Also
[Microsoft Graph Reference](dynamics_graph_reference.md)  
