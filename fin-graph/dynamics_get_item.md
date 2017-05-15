---
title: GET item method | Microsoft Docs
description: Gets an item.
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

# GET Item Method
Retrieve the properties and relationships of an item object for [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].


## HTTP request

```
GET /financials/companies/{id}/items/{id}
```

## Request headers
|Header|Value|
|------|-----|
|Authorization|Bearer. Required.|

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and items object in the response body.

## Example
**Request**

Here is an example of the request.
```json
GET https://graph.microsoft.com/v1.0/financials/companies/{id}/items/{id}
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
  "id": "id-value",
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
  "taxGroupCode": "FURNITURE",
  "lastModifiedDateTime": "2017-03-07T00:35:30.073Z"
}

```
## See Also
[Microsoft Graph Reference](dynamics_graph_reference.md)  
