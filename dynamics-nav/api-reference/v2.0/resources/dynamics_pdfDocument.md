---
title: pdfDocument resource type | Microsoft Docs
description: A pdf document object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/24/2020
ms.author: solsen
---

# pdfDocument resource type
Represents a pdf document in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods
| Method | Return Type|Description |
|:--------------------|:-----------|:-------------------------|
|[GET pdfDocument](../api/dynamics_pdfDocument_Get.md)|pdfDocument|Gets a pdf document object.|






## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|id|GUID|The unique ID of the item. Non-editable.|
|parentId|GUID|The ID of the parent entity. |
|parentType|NAV.attachmentEntityBufferDocumentType|The type of the parent document of the pdf document. It can be " ", "Journal", "Sales Order", "Sales Quote", "Sales Credit Memo", "Sales Invoice" or "Purchase Invoice".|
|pdfDocumentContent|stream|The content of the PDF document.|


## JSON representation

Here is a JSON representation of the pdfDocument resource.


```json
{
   "id": "GUID",
   "parentId": "GUID",
   "parentType": "NAV.attachmentEntityBufferDocumentType",
   "pdfDocumentContent": "stream"
}
```
## See also

[GET pdfDocument](../api/dynamics_pdfDocument_Get.md)

