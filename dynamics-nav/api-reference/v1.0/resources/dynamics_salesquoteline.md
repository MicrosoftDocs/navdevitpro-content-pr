---
title: salesQuoteLines resource type | Microsoft Docs
description: A sales quote line object in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/01/2019
ms.author: solsen
---

# salesQuoteLines resource type
Represents a salesQuoteLines resource type in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET salesQuoteLines](../api/dynamics_salesquoteline_get.md)|salesQuoteLines|Get a sales quote line object.|
|[POST salesQuoteLines](../api/dynamics_create_salesquoteline.md)|salesQuoteLines|Creates a sales quote line object.|
|[PATCH salesQuoteLines](../api/dynamics_salesquoteline_update.md)|salesQuoteLines|Updates a sales quote line object.|
|[DELETE salesQuoteLines](../api/dynamics_salesquoteline_delete.md)|none|Deletes a sales quote line object.|

## Properties

| Property     | Type   |Description|
|:---------------|:--------|:----------|
|documentId|GUID|The ID of the parent quote.|
|sequence|numeric|The line sequence number.|
|itemId|GUID|The Id of the item in the quote line.|
|accountId|GUID|The Id of the Account that will be used for this line. lineType will automatically be set to "Account" if this is set.|
|lineType|string|The type of the line. Can be Comment,Account,Item,Resource,Fixed Asset,Charge|
|lineDetails|complex|The details of the line.|
|description|string|A description of the item in the quote line.|
|unitOfMeasureId|GUID|The Id of the unit of measure in the quote line.|
|unitOfMeasure|[NAV.UnitOfMeasure](../resources/dynamics_complextypes.md)|The unit of measure complex type.|
|unitPrice|numeric|The unit price of each individual item in the quote line.|
|quantity|numeric|The quantity of the item in the quote line.|
|discountAmount|numeric|The line discount amount.|
|discountPercent|numeric|The line discount percent.|
|discountAppliedBeforeTax|boolean|Specified if the discount is applied before tax. Read-Only.|
|amountExcludingTax|numeric|The line amount excluding the tax. Read-Only.|
|taxCode|string|The tax code for the line.|
|taxPercent|decimal|The tax percent for the line.|
|totalTaxAmount|numeric|The total tax amount for the line. Read-Only.|
|amountIncludingTax|numeric|The total amount for the line including tax. Read-Only.|
|netAmount|numeric|The net amount is the amount including all discounts (taken from quote header). Read-Only.|
|netTaxAmount|numeric|The net tax amount is the tax amount calculated from net amount. Read-Only.|
|netAmountIncludingTax|numeric|The net amount including tax is the total net amount including tax. Read-Only.|

## Relationships
A Sales Quote (documentId) must exist in the Sales Quotes table.

An Item (itemId) must exist in the Item table.

An Account (accountId) must exist in the Accounts table.

A Unit of Measure (unitOfMeasure) must exist in the Unit of Measure table.

## JSON representation

Here is a JSON representation of the resource.


```json
  "value": [
    {
      "documentId": "GUID",
      "sequence": "decimal",
      "itemId": "GUID",
      "accountId": "GUID",
      "lineType": "String",
      "lineDetails": {NAV.documentLineObjectDetails},
      "description": "string",
      "unitOfMeasureId": "GUID",
      "unitOfMeasure": {NAV.UnitOfMeasure},
      "unitPrice": "decimal",
      "quantity": "decimal",
      "discountAmount": "decimal",
      "discountPercent": "decimal",
      "discountAppliedBeforeTax": "boolean",
      "amountExcludingTax": "decimal",
      "taxCode": "String",
      "taxPercent": "decimal",
      "totalTaxAmount": "decimal",
      "amountIncludingTax": "decimal",
      "netAmount": "decimal",
      "netTaxAmount": "decimal",
      "netAmountIncludingTax": "decimal"
    }
  ]
```

## See also

[Sales Quote Line](../resources/dynamics_salesquoteline.md)  
[Get Sales Quote Line](../api/dynamics_salesquoteline_get.md)  
[Create Sales Quote Line](../api/dynamics_create_salesquoteline.md)  
[Update Sales Quote Line](../api/dynamics_salesquoteline_update.md)  
[Delete Sales Quote Line](../api/dynamics_salesquoteline_delete.md)  