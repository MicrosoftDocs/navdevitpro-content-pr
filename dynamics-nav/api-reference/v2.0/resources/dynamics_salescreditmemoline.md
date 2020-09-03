---
title: salesCreditMemoLine resource type | Microsoft Docs
description: A sales credit memo line. 
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# salesCreditMemoLine resource type
Represents a line on a sales credit memo line in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET salesCreditMemoLine](../api/dynamics_salescreditmemoline_get.md)|salesCreditMemoLine|Gets a sales credit memo line object.|
|[POST salesCreditMemoLine](../api/dynamics_create_salescreditmemoline.md)|salesCreditMemoLine|Creates a sales credit memo line object.|
|[PATCH salesCreditMemoLine](../api/dynamics_salescreditmemoline_update.md)|salesCreditMemoLine|Updates a sales credit memo line object.|
|[DELETE salesCreditMemoLine](../api/dynamics_salescreditmemoline_delete.md)|none   |Deletes a sales credit memo line object.|


## Navigation

| Navigation |Return Type| Description |
|:----------|:----------|:-----------------|
|[salesCreditMemo](../resources/dynamics_salescreditmemo.md)|salesCreditMemo   |Gets the salescreditmemo of the salesCreditMemoLine.|
|[item](../resources/dynamics_item.md)|item   |Gets the item of the salesCreditMemoLine.|
|[account](../resources/dynamics_account.md)|account   |Gets the account of the salesCreditMemoLine.|
|[unitOfMeasure](../resources/dynamics_unitofmeasure.md)|unitOfMeasure   |Gets the unitofmeasure of the salesCreditMemoLine.|
|[itemVariant](../resources/dynamics_itemvariant.md)|itemVariant   |Gets the itemvariant of the salesCreditMemoLine.|
|[dimensionSetLines](../resources/dynamics_dimensionsetlines.md)|dimensionSetLines   |Gets the dimensionsetlines of the salesCreditMemoLine.|

## Properties

| Property     | Type   |Description|
|:---------------|:--------|:----------|
|documentId|GUID|The ID of the parent credit memo.|
|sequence|numeric|The line sequence number.|
|itemId|GUID|The Id of the item in the credit memo line.|
|accountId|GUID|The Id of the Account that will be used for this line. lineType will automatically be set to "Account" if this is set.|
|lineType|string|The type of the line. Can be Comment,Account,Item,Resource,Fixed Asset,Charge|
|lineDetails|complex|The details of the line.|
|description|string|A description of the item in the credit memo line.|
|unitOfMeasureId|GUID|The unit of measure for the credit memo line.|
|unitOfMeasure|[NAV.UnitOfMeasure](../resources/dynamics_complextypes.md)|The unit of measure complex type.|
|quantity|numeric|The quantity of the item in the credit memo line.|
|unitPrice|numeric|The unit price of each individual item in the credit memo line.|
|discountAmount|numeric|The line discount amount.|
|discountPercent|numeric|The line discount percent.|
|discountAppliedBeforeTax|boolean|Specified if the discount is applied before tax. Read-Only.|
|amountExcludingTax|numeric|The line amount excluding the tax. Read-Only.|
|taxCode|string|The tax code for the line.|
|taxPercent|numeric|The tax percent for the line. Read-Only.|
|totalTaxAmount|numeric|The total tax amount for the line. Read-Only.|
|amountIncludingTax|numeric|The total amount for the line including tax. Read-Only.|
|invoiceDiscountAllocation|numeric|The credit memo discount allocation is the credit memo discount distributed on the total amount. Read-Only.|
|netAmount|numeric|The net amount is the amount including all discounts (taken from credit memo header). Read-Only.|
|netTaxAmount|numeric|The net tax amount is the tax amount calculated from net amount. Read-Only.|
|netAmountIncludingTax|numeric|The net amount including tax is the total net amount including tax. Read-Only.|
|shipmentDate|date|The date the item in the line is expected to ship.|

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
   "unitPrice": "decimal",
   "quantity": "decimal",
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
   "itemVariantId": "GUID"
}
  ]
```

## See also

[Get Sales Credit Memo Line](../api/dynamics_salescreditmemoline_get.md)  
[Create Sales Credit Memo Line](../api/dynamics_create_salescreditmemoline.md)  
[Update Sales Credit Memo Line](../api/dynamics_salescreditmemoline_update.md)  
[Delete Sales Credit Memo Line](../api/dynamics_salescreditmemoline_delete.md)  