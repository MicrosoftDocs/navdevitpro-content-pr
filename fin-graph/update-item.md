---
title: UPDATE item method | Microsoft Docs
description: Updates an item.
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

# UPDATE Item Method
Update the properties of an item object for [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].

## Prerequisites

## HTTP request
An item from [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].
```
PATCH /financials/companies/{id}/items/{id}
```
## Optional query parameters

## Request headers

|Header|Value|
|------|-----|
|Authorization|Bearer . Required.|
|Content-Type|application/json.|

## Request body
In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

## Reponse
If successful, this method returns a 200 OK response code and an updated items object in the response body.

## Example
**Request**

Here is an example of the request.
```
PATCH https://graph.microsoft.com/beta/financials/companies/{id}/items{id}
Content-type: application/json

{
  "displayName": "ATHENS Desk - blocked",
  "blocked": true,
}
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```
HTTP/1.1 200 OK
Content-type: application/json

{
  "id": "4871857e-8a99-45f8-9ef0-2d2f56ef1dba",
  "number": "1896-S",
  "displayName": "ATHENS Desk - blocked",
  "type": "Inventory",
  "blocked": true,
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

## See Alsoapplication/json.
[Microsoft Graph Reference](graph-reference.md)  
