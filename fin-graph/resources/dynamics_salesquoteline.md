---
title: salesQuoteLine resource type | Microsoft Docs
description: A sales quote line.
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

# SalesQuoteLine resource type
Represents a salesQuoteLine resource type in Dynamics 365 for Financials.

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET Sales Quote Line](../api/dynamics_get_salesquoteline.md)|Sales Quote Line|Get Sales Quote Line object|
|[POST Sales Quote Line](../api/dynamics_create_salesquoteline.md)|Sales Quote Line|Create Sales Quote Line object|
|[PATCH Sales Quote Line](../api/dynamics_update_salesquoteline.md)|Sales Quote Line|Update Sales Quote Line object|
|[DELETE Sales Quote Line](../api/dynamics_delete_salesquoteline.md)|none|Delete Sales Quote Line object|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|documentId|GUID|The ID of the parent quote.|
|sequence|numeric|The line sequence number.|
|itemId|GUID|The Id of the item in the quote line.|
|accountId|GUID|The Id of the Account that will be used for this line. lineType will automatically be set to "Account" if this is set.|
|lineType|string|The type of the line. Can be Comment,Account,Item,Resource,Fixed Asset,Charge|
|lineDetails|complex|The details of the line.|
|description|string|A description of the item in the quote line.|
|unitOfMeasure|complex|The unit of measure complex type.|
|unitPrice|numeric|The unit price of each individual item in the quote line.|
|quantity|numeric|The quantity of the item in the quote line.|
|discountAmount|numeric|The line discount amount.|
|discountPercent|numeric|The line discount percent.|
|discountAppliedBeforeTax|boolean|Specified if the discount is applied before tax. Read-Only.|
|amountExcludingTax|numeric|The line amount excluding the tax. Read-Only.|
|taxCode|string|The tax code for the line.|
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
      "sequence": decimal,
      "itemId": "GUID",
      "accountId": "GUID",
      "lineType": "String",
      "lineDetails": {NAV.documentLineObjectDetails},
      "description": "String",
      "unitOfMeasure": {NAV.UnitOfMeasure},
      "unitPrice": decimal,
      "quantity": decimal,
      "discountAmount": decimal,
      "discountPercent": decimal,
      "discountAppliedBeforeTax": false,
      "amountExcludingTax": decimal,
      "taxCode": "String",
      "taxPercent": decimal,
      "totalTaxAmount": decimal,
      "amountIncludingTax": decimal,
      "netAmount": decimal,
      "netTaxAmount": decimal,
      "netAmountIncludingTax": decimal
    }
  ]

```

## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 
