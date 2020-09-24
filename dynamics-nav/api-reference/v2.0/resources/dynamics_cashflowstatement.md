---
title: cashFlowStatement resource type | Microsoft Docs
description: A cash flow statement object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/01/2020
ms.author: solsen
---

# cashFlowStatement resource type
Represents a cash flow statement in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods
| Method | Return Type|Description |
|:--------------------|:-----------|:-------------------------|
|[GET cashFlowStatement](../api/dynamics_cashFlowStatement_Get.md)|cashFlowStatement|Gets a cash flow statement object.|






## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|id|GUID|The unique ID of the item. Non-editable.|
|lineNumber|integer|The cash flow statement item line number.|
|display|string|The cash flow statement item display name.|
|netChange|decimal|The cash flow statement net change. |
|lineType|string|The type of the cash flow statement.|
|indentation|integer|The cash flow statement item indentation used in report layout.|
|dateFilter|date|The date filter used to calculate the cash flow statement items.|


## JSON representation

Here is a JSON representation of the cashFlowStatement resource.


```json
{
   "id": "GUID",
   "lineNumber": "integer",
   "display": "string",
   "netChange": "decimal",
   "lineType": "string",
   "indentation": "integer",
   "dateFilter": "date"
}
```
## See also

[GET cashFlowStatement](../api/dynamics_cashFlowStatement_Get.md)   

