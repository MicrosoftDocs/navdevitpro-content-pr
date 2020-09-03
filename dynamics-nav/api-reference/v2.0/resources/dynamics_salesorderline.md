---
title: salesOrderLine resource type | Microsoft Docs
description: A sales order line object in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# salesOrderLine resource type
Represents a line on a sales order in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET salesOrderLine](../api/dynamics_salesorderline_get.md)|salesOrderLine|Gets a sales order line object.|
|[POST salesOrderLine](../api/dynamics_create_salesorderline.md)|salesOrderLine|Creates a sales order line object.|
|[PATCH salesOrderLine](../api/dynamics_salesorderline_update.md)|salesOrderLine|Updates a sales order line object.|
|[DELETE salesOrderLine](../api/dynamics_salesorderline_delete.md)|none|Deletes a sales order line object.|


## Navigation

| Navigation |Return Type| Description |
|:----------|:----------|:-----------------|
|[salesOrder](../resources/dynamics_salesorder.md)|salesOrder   |Gets the salesorder of the salesOrderLine.|
|[item](../resources/dynamics_item.md)|item   |Gets the item of the salesOrderLine.|
|[account](../resources/dynamics_account.md)|account   |Gets the account of the salesOrderLine.|
|[unitOfMeasure](../resources/dynamics_unitofmeasure.md)|unitOfMeasure   |Gets the unitofmeasure of the salesOrderLine.|
|[itemVariant](../resources/dynamics_itemvariant.md)|itemVariant   |Gets the itemvariant of the salesOrderLine.|
|[dimensionSetLines](../resources/dynamics_dimensionsetlines.md)|dimensionSetLines   |Gets the dimensionsetlines of the salesOrderLine.|

## Properties

| Property     | Type   |Description|
|:---------------|:--------|:----------|
|id|GUID|The ID of the order line.|
|documentId|GUID|The ID of the parent order.|
|sequence|numeric|The line sequence number.|
|itemId|GUID|The Id of the item in the order line.|
|accountId|GUID|The Id of the Account that will be used for this line. lineType will automatically be set to "Account" if this is set.|
|lineType|string|The type of the line. Can be Comment,Account,Item,Resource,Fixed Asset,Charge|
|lineDetails|complex|The details of the line.|
|description|string|A description of the item in the order line.|
|unitOfMeasureId|GUID|The Id of the unit of measure in the order line.|
|unitOfMeasure|[NAV.UnitOfMeasure](../resources/dynamics_complextypes.md)|The unit of measure complex type.|
|quantity|numeric|The quantity of the item in the order line.|
|unitPrice|numeric|The unit price of each individual item in the order line.|
|discountAmount|numeric|The line discount amount.|
|discountPercent|numeric|The line discount percent.|
|discountAppliedBeforeTax|boolean|Specified if the discount is applied before tax. Read-Only.|
|amountExcludingTax|numeric|The line amount excluding the tax. Read-Only.|
|taxCode|string|The tax code for the line.|
|taxPercent|numeric|The tax percent for the line. Read-Only.|
|totalTaxAmount|numeric|The total tax amount for the line. Read-Only.|
|amountIncludingTax|numeric|The total amount for the line including tax. Read-Only.|
|invoiceDiscountAllocation|numeric|The invoice discount allocation is the order discount distributed on the total amount. Read-Only.|
|netAmount|numeric|The net amount is the amount including all discounts (taken from order header). Read-Only.|
|netTaxAmount|numeric|The net tax amount is the tax amount calculated from net amount. Read-Only.|
|netAmountIncludingTax|numeric|The net amount including tax is the total net amount including tax. Read-Only.|
|shipmentDate|date|The date the item in the line is expected to ship.|
|shippedQuantity|numeric|The quantity of items from the order already shipped.|
|invoicedQuantity|numeric|The quantity of items from the order already invoiced.|
|invoiceQuantity|numeric|The quantity of items from the order to be invoiced.|
|shipQuantity|numeric|The quantity of items from the order to be shipped.|

## JSON representation

Here is a JSON representation of the resource.


```json
  "value": [
    {
   "id": "GUID",
   "documentId": "GUID",
   "sequence": "integer",
   "itemId": "GUID",
   "accountId": "GUID",
   "lineType": "NAV.invoiceLineAggLineType",
   "lineObjectNumber": "string",
   "description": "string",
   "unitOfMeasureId": "GUID",
   "unitOfMeasureCode": "string",
   "quantity": "decimal",
   "unitPrice": "decimal",
   "discountAmount": "decimal",
   "discountPercent": "decimal",
   "discountAppliedBeforeTax": "boolean",
   "amountExcludingTax": "decimal",
   "taxCode": "string",
   "taxPercent": "decimal",
   "totalTaxAmount": "decimal",
   "amountIncludingTax": "decimal",
   "invoiceDiscountAllocation": "decimal",
   "netAmount": "decimal",
   "netTaxAmount": "decimal",
   "netAmountIncludingTax": "decimal",
   "shipmentDate": "date",
   "shippedQuantity": "decimal",
   "invoicedQuantity": "decimal",
   "invoiceQuantity": "decimal",
   "shipQuantity": "decimal",
   "itemVariantId": "GUID"
}
  ]
```

## See also

[Get Sales Order Line](../api/dynamics_salesorderline_get.md)  
[Create Sales Order Line](../api/dynamics_create_salesorderline.md)  
[Update Sales Order Line](../api/dynamics_salesorderline_update.md)  
[Delete Sales Order Line](../api/dynamics_salesorderline_delete.md)  