---
title: dimensionSetLine resource type | Microsoft Docs
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

# dimensionSetLine resource type
Represents a line on a sales invoice in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method                                                                | Return Type      | Description                    |
|:----------------------------------------------------------------------|:-----------------|:-------------------------------|
|[GET dimensionSetLine](../api/dynamics_salesinvoiceline_get.md)      |dimensionSetLine|Gets a sales invoice line object   |
|[POST dimensionSetLine](../api/dynamics_create_salesinvoiceline.md)  |dimensionSetLine|Creates a sales invoice line object.|
|[PATCH dimensionSetLine](../api/dynamics_salesinvoiceline_update.md) |dimensionSetLine|Updated a sales invoice line object.|
|[DELETE dimensionSetLine](../api/dynamics_salesinvoiceline_delete.md)|none              |Deletes a sales invoice line object.|


## Navigation

| Navigation |Return Type| Description |
|:----------|:----------|:-----------------|
|[salesInvoice](../resources/dynamics_salesinvoice.md)|salesInvoice   |Gets the salesinvoice of the dimensionSetLine.|
|[salesInvoiceLine](../resources/dynamics_salesinvoiceline.md)|salesInvoiceLine   |Gets the salesinvoiceline of the dimensionSetLine.|
|[dimension](../resources/dynamics_dimension.md)|dimension   |Gets the dimension of the dimensionSetLine.|
|[journalLine](../resources/dynamics_journalline.md)|journalLine   |Gets the journalline of the dimensionSetLine.|
|[timeRegistrationEntry](../resources/dynamics_timeregistrationentry.md)|timeRegistrationEntry   |Gets the timeregistrationentry of the dimensionSetLine.|
|[generalLedgerEntry](../resources/dynamics_generalledgerentry.md)|generalLedgerEntry   |Gets the generalledgerentry of the dimensionSetLine.|
|[salesOrder](../resources/dynamics_salesorder.md)|salesOrder   |Gets the salesorder of the dimensionSetLine.|
|[salesOrderLine](../resources/dynamics_salesorderline.md)|salesOrderLine   |Gets the salesorderline of the dimensionSetLine.|
|[salesQuote](../resources/dynamics_salesquote.md)|salesQuote   |Gets the salesquote of the dimensionSetLine.|
|[salesQuoteLine](../resources/dynamics_salesquoteline.md)|salesQuoteLine   |Gets the salesquoteline of the dimensionSetLine.|
|[salesCreditMemo](../resources/dynamics_salescreditmemo.md)|salesCreditMemo   |Gets the salescreditmemo of the dimensionSetLine.|
|[salesCreditMemoLine](../resources/dynamics_salescreditmemoline.md)|salesCreditMemoLine   |Gets the salescreditmemoline of the dimensionSetLine.|
|[purchaseInvoice](../resources/dynamics_purchaseinvoice.md)|purchaseInvoice   |Gets the purchaseinvoice of the dimensionSetLine.|
|[purchaseInvoiceLine](../resources/dynamics_purchaseinvoiceline.md)|purchaseInvoiceLine   |Gets the purchaseinvoiceline of the dimensionSetLine.|

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
   "code": "string",
   "parentId": "GUID",
   "parentType": "string",
   "displayName": "string",
   "valueId": "GUID",
   "valueCode": "string",
   "valueDisplayName": "string"
}
  ]
```

## See also

[Get Sales Invoice Line](../api/dynamics_salesinvoiceline_get.md)  
[Create Sales Invoice Line](../api/dynamics_create_salesinvoiceline.md)  
[Update Sales Invoice Line](../api/dynamics_salesinvoiceline_update.md)  
[Delete Sales Invoice Line](../api/dynamics_salesinvoiceline_delete.md)  