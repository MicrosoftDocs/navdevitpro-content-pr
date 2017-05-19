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

# SalesInvoiceLine resource type
Represents a salesInvoiceLine resource type in Dynamics 365 for Financials.

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET Sales Invoice Line](../api/dynamics_get_salesinvoiceline.md)|Sales Invoice Line|Get Sales Invoice Line object|
|[POST Sales Invoice Line](../api/dynamics_create_salesinvoiceline.md)|Sales Invoice Line|Create Sales Invoice Line object|
|[PATCH Sales Invoice Line](../api/dynamics_update_salesinvoiceline.md)|Sales Invoice Line|Update Sales Invoice Line object|
|[DELETE Sales Invoice Line](../api/dynamics_delete_salesinvoiceline.md)|none|Delete Sales Invoice Line object|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|documentId|GUID|The ID of the parent invoice.|
|sequence|numeric|The line sequence number.|
|itemId|GUID|The Id of the item in the invoice line.|
|accountId|GUID|The Id of the Account that will be used for this line. lineType will automatically be set to "Account" if this is set.|
|lineType|string|The type of the line. Can be Comment,Account,Item,Resource,Fixed Asset,Charge|
|lineDetails|complex|The details of the line.|
|description|string|A description of the item in the invoice line.|
|unitOfMeasure|complex|The unit of measure complex type.|
|quantity|numeric|The quantity of the item in the invoice line.|
|unitPrice|numeric|The unit price of each individual item in the invoice line.|
|discountAmount|numeric|The line discount amount.|
|discountPercent|numeric|The line discount percent.|
|discountAppliedBeforeTax|boolean|Specified if the discount is applied before tax. Read-Only.|
|amountExcludingTax|numeric|The line amount excluding the tax. Read-Only.|
|taxCode|string|The tax code for the line.|
|taxPercent|numeric|The tax percent for the line. Read-Only.|
|totalTaxAmount|numeric|The total tax amount for the line. Read-Only.|
|amountIncludingTax|numeric|The total amount for the line including tax. Read-Only.|
|invoiceDiscountAllocation|numeric|The invoice discount allocation is the invoice discount distributed on the total amount. Read-Only.|
|netAmount|numeric|The net amount is the amount including all discounts (taken from invoice header). Read-Only.|
|netTaxAmount|numeric|The net tax amount is the tax amount calculated from net amount. Read-Only.|
|netAmountIncludingTax|numeric|The net amount including tax is the total net amount including tax. Read-Only.|
|shipmentDate|date|The date the item in the line is expected to ship.|

## Relationships
A Sales Invoice (documentId) must exist in the Sales Invoices table.

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
      "invoiceDiscountAllocation": decimal,
      "netAmount": decimal,
      "netTaxAmount": decimal,
      "netAmountIncludingTax": decimal,
      "shipmentDate": "Date"
    }
  ]

```

## See also
[Working with Dynamics 365 for Finance and Operations, Business Edition in Microsoft Graph](dynamics_overview.md)  
