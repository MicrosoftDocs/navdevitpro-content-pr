---
title: cashFlowStatement resource type | Microsoft Docs
description: A cash flow statement object in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/01/2019
ms.author: solsen
---

# cashFlowStatement resource type
Represents an cashFlowStatement object in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method       | Return Type  |Description|
|:-------------|:-------------|:----------|
|[GET cashFlowStatement](../api/dynamics_cashflowstatement_get.md)|cashFlowStatement|Get a cashFlowStatement object.|

## Properties

| Property     | Type   |Description                              |
|:-------------|:-------|:----------------------------------------|
|lineNumber    |numeric |The cashFlowStatement item line number.  |
|display       |string  |The cashFlowStatement item display name. |
|netChange     |numeric |The cashFlowStatement item Net Change.   |
|lineType      |string  |The cashFlowStatement item line type can be: header, detail, total, or spacer.|
|indentation   |numeric |The cashFlowStatement item indentation used in report layout.|
|dateFilter    |date    |The date filter used to calculate the cashFlowStatement items.|


## Relationships
None

## JSON representation

Here is a JSON representation of the resource.


```json
{
    "lineNumber": "int",
    "display": "string",
    "netChange": "decimal",
    "lineType": "string",
    "indentation": "int",
    "dateFilter": "date"
}
```
## See also
  
[Get Cash Flow Statement](../api/dynamics_cashflowstatement_get.md)  
[Balance Sheet](dynamics_balancesheet.md)  
