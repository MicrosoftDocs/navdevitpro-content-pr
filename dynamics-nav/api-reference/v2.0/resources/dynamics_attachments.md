---
title: attachments resource type | Microsoft Docs
description: A sales invoice line in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# attachments resource type
Represents a line on a sales invoice in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method                                                                | Return Type      | Description                    |
|:----------------------------------------------------------------------|:-----------------|:-------------------------------|
|[GET attachments](../api/dynamics_salesinvoiceline_get.md)      |attachments|Gets a sales invoice line object   |
|[POST attachments](../api/dynamics_create_salesinvoiceline.md)  |attachments|Creates a sales invoice line object.|
|[PATCH attachments](../api/dynamics_salesinvoiceline_update.md) |attachments|Updated a sales invoice line object.|
|[DELETE attachments](../api/dynamics_salesinvoiceline_delete.md)|none              |Deletes a sales invoice line object.|


## Navigation

| Navigation |Return Type| Description |
|:----------|:----------|:-----------------|
|[salesInvoice](../resources/dynamics_salesinvoice.md)|salesInvoice   |Gets the salesinvoice of the attachments.|
|[journalLine](../resources/dynamics_journalline.md)|journalLine   |Gets the journalline of the attachments.|
|[generalLedgerEntry](../resources/dynamics_generalledgerentry.md)|generalLedgerEntry   |Gets the generalledgerentry of the attachments.|
|[salesOrder](../resources/dynamics_salesorder.md)|salesOrder   |Gets the salesorder of the attachments.|
|[salesQuote](../resources/dynamics_salesquote.md)|salesQuote   |Gets the salesquote of the attachments.|
|[salesCreditMemo](../resources/dynamics_salescreditmemo.md)|salesCreditMemo   |Gets the salescreditmemo of the attachments.|
|[purchaseInvoice](../resources/dynamics_purchaseinvoice.md)|purchaseInvoice   |Gets the purchaseinvoice of the attachments.|

## Properties

| Property                | Type    | Description                                               |
|:------------------------|:------|:----------------------------------------------------------|
|documentId               |GUID   |The ID of the parent invoice.                              |
|sequence                 |numeric|The line sequence number.                                  |
|itemId                   |GUID   |The Id of the item in the invoice line.                    |
|accountId                |GUID   |The Id of the Account that will be used for this line. lineType will automatically be set to "Account" if this is set.|
|lineType                 |string |The type of the line. Can be Comment,Account,Item,Resource,Fixed Asset,Charge|
|lineDetails              |complex|The details of the line.                                   |
|description              |string |A description of the item in the invoice line.             |
|unitOfMeasureId          |GUID   |The unit of measure for the invoice line.                  |
|unitOfMeasure            |[NAV.UnitOfMeasure](../resources/dynamics_complextypes.md)|The unit of measure complex type.|
|quantity                 |numeric|The quantity of the item in the invoice line.              |
|unitPrice                |numeric|The unit price of each individual item in the invoice line.|
|discountAmount           |numeric|The line discount amount.                                  |
|discountPercent          |numeric|The line discount percent.                                 |
|discountAppliedBeforeTax |boolean|Specified if the discount is applied before tax. Read-Only.|
|amountExcludingTax       |numeric|The line amount excluding the tax. Read-Only.              |
|taxCode                  |string |The tax code for the line.                                 |
|taxPercent               |numeric|The tax percent for the line. Read-Only.                   |
|totalTaxAmount           |numeric|The total tax amount for the line. Read-Only.              |
|amountIncludingTax       |numeric|The total amount for the line including tax. Read-Only.    |
|invoiceDiscountAllocation|numeric|The invoice discount allocation is the invoice discount distributed on the total amount. Read-Only.|
|netAmount                |numeric|The net amount is the amount including all discounts (taken from invoice header). Read-Only.|
|netTaxAmount             |numeric|The net tax amount is the tax amount calculated from net amount. Read-Only.|
|netAmountIncludingTax    |numeric|The net amount including tax is the total net amount including tax. Read-Only.|
|shipmentDate             |date   |The date the item in the line is expected to ship.         |

## JSON representation

Here is a JSON representation of the resource.


```json
  "value": [
    {
   "id": "GUID",
   "parentId": "GUID",
   "fileName": "string",
   "byteSize": "integer",
   "attachmentContent": "stream",
   "lastModifiedDateTime": "datetime",
   "parentType": "string"