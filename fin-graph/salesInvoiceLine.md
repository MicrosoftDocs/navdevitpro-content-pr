---
title: salesInvoiceLine resource type | Microsoft Docs
description: A sales invoice line.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/02/2017
ms.author: solsen
---

# salesInvoiceLine resource type

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|GET Sales Invoice Line|Sales Invoice Line|Get Sales Invoice Line object|
|POST Sales Invoice Line|Sales Invoice Line|Create Sales Invoice Line object|
|PATCH Sales Invoice Line|Sales Invoice Line|Update Sales Invoice Line object|
|DELETE Sales Invoice Line|none|Delete Sales Invoice Line object|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|Document_Id|GUID|The id of the parent invoice.|
|Line_No|numeric|The line sequence number.|
|itemId|GUID|The id of the item in the invoice line.|
|itemNumber|string|The number of the item in the invoice line.|
|itemDisplayName|string|The display name of the item in the invoice line.|
|itemDescription|string|A description of the item in the invoice line.|
|quantity|numeric|The quantity of the item in the invoice line.|
|unitPrice|numeric|The unit price of each individual item in the invoice line.|
|discountAmount|numeric|The line discount amount.|
|discountPercent|numeric|The line discount percent.|
|discountAppliedBeforeTax|boolean|Specified if the discount is applied before tax.|
|amountExcludingTax|numeric|The line amount excluding the tax.|
|taxCode|string|The tax code for the line.|
|taxPercent|numeric|The tax percent for the line.|
|totalTaxAmount|numeric|The total tax amount for the line.|
|amountIncludingTax|numeric|The total amount for the line including tax.|
|expectedShipDate|date|The date the item in the line is expected to ship.|

## Relationships
None

## JSON representation

Here is a JSON representation of the resource.


```json
  "value": [
      {
      "Document_Id": "GUID",
      "Line_No": decimal,
      "itemId": "GUID",
      "itemNumber": "String",
      "itemDisplayName": "String",
      "itemDescription": "",
      "quantity": decimal,
      "unitPrice": decimal,
      "discountAmount": 0,
      "discountPercent": 0,
      "discountAppliedBeforeTax": false,
      "amountExcludingTax": decimal,
      "taxCode": "String",
      "taxPercent": decimal,
      "totalTaxAmount": decimal,
      "amountIncludingTax": decimal,
      "expectedShipDate": "Date"
      }
]

```

## See Also
[Graph Reference](graph-reference.md)  
