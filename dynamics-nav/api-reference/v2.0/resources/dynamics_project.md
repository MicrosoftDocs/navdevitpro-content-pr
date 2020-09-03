---
title: project resource type | Microsoft Docs
description: A project object in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# project resource type
Represents a project in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET project](../api/dynamics_project_get.md)|project|Gets a Project object.|
|[POST project](../api/dynamics_create_project.md)|project|Creates a Project object.|
|[PATCH project](../api/dynamics_project_update.md)|project|Updates a Project object.|
|[DELETE project](../api/dynamics_project_delete.md)|none   |Deletes a Project object.|


## Navigation

| Navigation |Return Type| Description |
|:----------|:----------|:-----------------|
|[purchaseInvoice](../resources/dynamics_purchaseinvoice.md)|purchaseInvoice   |Gets the purchaseinvoice of the project.|
|[item](../resources/dynamics_item.md)|item   |Gets the item of the project.|
|[account](../resources/dynamics_account.md)|account   |Gets the account of the project.|
|[unitOfMeasure](../resources/dynamics_unitofmeasure.md)|unitOfMeasure   |Gets the unitofmeasure of the project.|
|[itemVariant](../resources/dynamics_itemvariant.md)|itemVariant   |Gets the itemvariant of the project.|
|[dimensionSetLines](../resources/dynamics_dimensionsetlines.md)|dimensionSetLines   |Gets the dimensionsetlines of the project.|



## Properties

| Property     | Type   |Description|
|:---------------|:--------|:----------|
|documentId|GUID|The ID of the parent invoice.|
|sequence|numeric|The line sequence number.|
|itemId|GUID|The Id of the item in the invoice line.|
|accountId|GUID|The Id of the Account that will be used for this line. lineType will automatically be set to "Account" if this is set.|
|lineType|string|The type of the line. Can be Comment,Account,Item,Resource,Fixed Asset,Charge|
|lineDetails|complex|The details of the line.|
|description|string|A description of the item in the invoice line.|
|unitOfMeasure|[NAV.UnitOfMeasure](../resources/dynamics_complextypes.md)|The unit of measure complex type.|
|unitCost|numeric|The unit cost of each individual item in the invoice line.|
|quantity|numeric|The quantity of the item in the invoice line.|
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
|expectedReceiptDate|date|The date the item in the line is expected to be received.|

## JSON representation

Here is a JSON representation of the resource.


```json
  "value": [
    {
   "id": "GUID",
   "number": "string",
   "displayName": "string"
}
  ]
```

## See also

[Get Project](../api/dynamics_project_get.md)  
[Create Project](../api/dynamics_create_project.md)  
[Update Project](../api/dynamics_project_update.md)  
[Delete Project](../api/dynamics_project_delete.md)  