---
title: salesCreditMemoLine resource type | Microsoft Docs
description: A sales credit memo line object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/15/2020
ms.author: solsen
---

# salesCreditMemoLine resource type
Represents an sales credit memo line in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method              | Return Type|Description               |
|:--------------------|:-----------|:-------------------------|
|[GET salesCreditMemoLine](../api/dynamics_salesCreditMemoLine_Get.md)|salesCreditMemoLine|Gets a sales credit memo line object.|
|[DELETE salesCreditMemoLine](../api/dynamics_salesCreditMemoLine_Delete.md)|salesCreditMemoLine|Deletes a sales credit memo line object.|
|[POST salesCreditMemoLine](../api/dynamics_salesCreditMemoLine_Create.md)|salesCreditMemoLine|Creates a sales credit memo line object.|
|[PATCH salesCreditMemoLine](../api/dynamics_salesCreditMemoLine_Update.md)|salesCreditMemoLine|Updates a sales credit memo line object.|




## Navigation

| Navigation |Return Type| Description |    
|:----------|:----------|:-----------------|
|[salesCreditMemo](../resources/dynamics_salescreditmemo.md)|salesCreditMemo |Gets the salescreditmemo of the salesCreditMemoLine.|
|[item](../resources/dynamics_item.md)|item |Gets the item of the salesCreditMemoLine.|
|[account](../resources/dynamics_account.md)|account |Gets the account of the salesCreditMemoLine.|
|[unitOfMeasure](../resources/dynamics_unitofmeasure.md)|unitOfMeasure |Gets the unitofmeasure of the salesCreditMemoLine.|
|[itemVariant](../resources/dynamics_itemvariant.md)|itemVariant |Gets the itemvariant of the salesCreditMemoLine.|
|[dimensionSetLines](../resources/dynamics_dimensionsetlines.md)|dimensionSetLines |Gets the dimensionsetlines of the salesCreditMemoLine.|


## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|id|GUID|The unique ID of the item. Non-editable.|
|documentId|GUID|The ID of the parent sales credit memo line. |
|sequence|integer|The line sequence number.|
|itemId|GUID|The ID of the item in the sales credit memo line.|
|accountId|GUID|The id of the account that the sales credit memo line is related to. |
|lineType|[NAV.invoiceLineAggLineType](../resources/dynamics_complextypes.md)|The type of thesales credit memo line. It can be "Comment", "Account", "Item", "Resource" Value=", "Fixed Asset" or "Charge".|
|lineObjectNumber|string|The number of the object (account or item) of the sales credit memo line.|
|description|string|Specifies the description of the sales credit memo line.|
|unitOfMeasureId|GUID|The ID of unit of measure for the sales credit memo line.|
|unitOfMeasureCode|string|The code of unit of measure for the sales credit memo line.|
|unitPrice|decimal|Specifies the price for one unit of the item in the specified sales credit memo line.|
|quantity|decimal|The quantity of the item in the sales credit memo line.|
|discountAmount|decimal|The sales credit memo line discount amount.|
|discountPercent|decimal|The line discount percent.    |
|discountAppliedBeforeTax|boolean|Specifies whether the discount is applied before tax.|
|amountExcludingTax|decimal|The line amount excluding the tax. Read-Only.|
|taxCode|string|The tax code for the line.       |
|taxPercent|decimal|The tax percent for the line. Read-Only.|
|totalTaxAmount|decimal|The total tax amount for the sales credit memo line. Read-Only.|
|amountIncludingTax|decimal|The total amount for the line including tax. Read-Only.|
|invoiceDiscountAllocation|decimal|The sales credit memo line discount allocation is the sales credit memo line discount distributed on the total amount. Read-Only.|
|netAmount|decimal|The net amount is the amount including all discounts (taken from the sales credit memo line). Read-Only.|
|netTaxAmount|decimal|The net tax amount is the tax amount calculated from net amount. Read-Only.|
|netAmountIncludingTax|decimal|The net amount including tax is the total net amount including tax. Read-Only.|
|shipmentDate|date|The date the item in the line is expected to ship.|
|itemVariantId|GUID|The ID of the item variant in the sales credit memo line.|


## JSON representation

Here is a JSON representation of the salesCreditMemoLine resource.


```json
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
```
## See also

[GET salesCreditMemoLine](../api/dynamics_salesCreditMemoLine_Get.md)
[DELETE salesCreditMemoLine](../api/dynamics_salesCreditMemoLine_Delete.md)
[POST salesCreditMemoLine](../api/dynamics_salesCreditMemoLine_Create.md)
[PATCH salesCreditMemoLine](../api/dynamics_salesCreditMemoLine_Update.md)

