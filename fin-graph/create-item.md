---
title: CREATE item method | Microsoft Docs
description: Gets a sales invoice line.
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

# CREATE Item Method
Create an item in Dynamics 365 Financials for use on invoices, quotes, etc.

## Prerequisites

## HTTP request
```
POST /financials/companies/{id}/items
```
## Optional query parameters

## Request headers

|Header|Value|
|------|-----|
|Authorization|Bearer. Required.|
|Content-Type|application/json|

## Request body
In the request body, supply a JSON representation of items object.

## Reponse
If successful, this method returns 201, Created response code and items object in the response body.

## Example
**Request**

Here is an example of a request.

```
POST https://graph.microsoft.com/beta/finacials/companies/{id}/items
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
In the request body, supply a JSON representation of items object.

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```
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
[Microsoft Graph Reference](graph-reference.md)  
