---
title: purchaseReceiptLine resource type | Microsoft Docs
description: A purchase receipt line object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: "dynamics365-business-central"
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/22/2020
ms.author: solsen
---

# purchaseReceiptLine resource type

[!INCLUDE[api_v2_note](../../includes/api_v2_note.md)]

Represents a purchase receipt line in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods
| Method | Return Type|Description |
|:--------------------|:-----------|:-------------------------|
|[GET purchaseReceiptLine](../api/dynamics_purchaseReceiptLine_Get.md)|purchaseReceiptLine|Gets a purchase receipt line object.|




## Navigation

| Navigation |Return Type| Description | 
 |:----------|:----------|:-----------------|
|[account](dynamics_account.md)|account |Gets the account of the purchaseReceiptLine.|
|[dimensionSetLines](dynamics_dimensionsetline.md)|dimensionSetLines |Gets the dimensionsetlines of the purchaseReceiptLine.|


## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|id|GUID|The unique ID of the item. Non-editable.|
|documentId|GUID|The ID of the parent purchase receipt line. |
|sequence|integer|The line sequence number.|
|lineType|NAV.purchaseLineType||
|lineObjectNumber|string|The number of the object (account or item) of the purchase receipt line.|
|description|string|Specifies the description of the purchase receipt line.|
|unitOfMeasureCode|string|The code of unit of measure for the purchase receipt line.|
|unitCost|decimal|The unit cost of each individual item in the purchase receipt line.|
|quantity|decimal|The quantity of the item in the purchase receipt line.|
|discountPercent|decimal|The line discount percent.    |
|taxPercent|decimal|The tax percent for the line. Read-Only.|
|expectedReceiptDate|date|The date the item in the line is expected to be received.|


## JSON representation

Here is a JSON representation of the purchaseReceiptLine resource.


```json
{
   "id": "GUID",
   "documentId": "GUID",
   "sequence": "integer",
   "lineType": "NAV.purchaseLineType",
   "lineObjectNumber": "string",
   "description": "string",
   "unitOfMeasureCode": "string",
   "unitCost": "decimal",
   "quantity": "decimal",
   "discountPercent": "decimal",
   "taxPercent": "decimal",
   "expectedReceiptDate": "date"
}
```
## See also

[GET purchaseReceiptLine](../api/dynamics_purchaseReceiptLine_Get.md)   

