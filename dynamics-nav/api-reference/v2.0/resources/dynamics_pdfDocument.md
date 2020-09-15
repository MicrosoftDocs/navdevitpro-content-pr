---
title: pdfDocument resource type | Microsoft Docs
description: A pdf document object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/15/2020
ms.author: solsen
---

# pdfDocument resource type
Represents an pdf document in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method              | Return Type|Description               |
|:--------------------|:-----------|:-------------------------|
|[GET pdfDocument](../api/dynamics_pdfDocument_Get.md)|pdfDocument|Gets a pdf document object.|
|[DELETE pdfDocument](../api/dynamics_pdfDocument_Delete.md)|pdfDocument|Deletes a pdf document object.|
|[POST pdfDocument](../api/dynamics_pdfDocument_Create.md)|pdfDocument|Creates a pdf document object.|
|[PATCH pdfDocument](../api/dynamics_pdfDocument_Update.md)|pdfDocument|Updates a pdf document object.|






## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|id|GUID|The unique ID of the item. Non-editable.|
|content|stream|The pdf document's content.|


## JSON representation

Here is a JSON representation of the pdfDocument resource.


```json
{
   "id": "GUID",
   "content": "stream"
}
```
## See also

[GET pdfDocument](../api/dynamics_pdfDocument_Get.md)
[DELETE pdfDocument](../api/dynamics_pdfDocument_Delete.md)
[POST pdfDocument](../api/dynamics_pdfDocument_Create.md)
[PATCH pdfDocument](../api/dynamics_pdfDocument_Update.md)

