---
title: retainedEarningsStatement resource type | Microsoft Docs
description: A retained earnings statement object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/15/2020
ms.author: solsen
---

# retainedEarningsStatement resource type
Represents an retained earnings statement in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method              | Return Type|Description               |
|:--------------------|:-----------|:-------------------------|
|[GET retainedEarningsStatement](../api/dynamics_retainedEarningsStatement_Get.md)|retainedEarningsStatement|Gets a retained earnings statement object.|
|[DELETE retainedEarningsStatement](../api/dynamics_retainedEarningsStatement_Delete.md)|retainedEarningsStatement|Deletes a retained earnings statement object.|
|[POST retainedEarningsStatement](../api/dynamics_retainedEarningsStatement_Create.md)|retainedEarningsStatement|Creates a retained earnings statement object.|
|[PATCH retainedEarningsStatement](../api/dynamics_retainedEarningsStatement_Update.md)|retainedEarningsStatement|Updates a retained earnings statement object.|






## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|id|GUID|The unique ID of the item. Non-editable.|
|lineNumber|integer|The retained earnings statement item line number.|
|display|string|The retained earnings statement item display name.|
|netChange|decimal|The retained earnings statement net change. |
|lineType|string|The type of the retained earnings statement.|
|indentation|integer|The retained earnings statement item indentation used in report layout.|
|dateFilter|date|The date filter used to calculate the retained earnings statement items.|


## JSON representation

Here is a JSON representation of the retainedEarningsStatement resource.


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

[GET retainedEarningsStatement](../api/dynamics_retainedEarningsStatement_Get.md)
[DELETE retainedEarningsStatement](../api/dynamics_retainedEarningsStatement_Delete.md)
[POST retainedEarningsStatement](../api/dynamics_retainedEarningsStatement_Create.md)
[PATCH retainedEarningsStatement](../api/dynamics_retainedEarningsStatement_Update.md)

