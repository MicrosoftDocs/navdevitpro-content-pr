---
title: unitOfMeasure resource type | Microsoft Docs
description: A unit of measure object in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# unitOfMeasure resource type
Represents a unit of measure in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method       | Return Type  |Description          |
|:-------------|:-------------|:--------------------|
|[GET unitOfMeasure](../api/dynamics_unitofmeasure_get.md)|unitOfMeasure|Get a retained earnings statement object.|

## Properties

| Property  | Type  |Description                                                           |
|:----------|:------|:---------------------------------------------------------------------|
|lineNumber |numeric|The unitOfMeasure item line number.                       |
|display    |string |The unitOfMeasure item display name.                      |
|netChange  |numeric|The unitOfMeasure item Net Change.                        |
|lineType   |string |The unitOfMeasure item line type can be: header, detail, total, or spacer.|
|indentation|numeric|The unitOfMeasure item indentation used in report layout. |
|dateFilter |date   |The date filter used to calculate the unitOfMeasure items.|


## JSON representation

Here is a JSON representation of the resource.


```json
{
   "id": "GUID",
   "code": "string",
   "displayName": "string",
   "internationalStandardCode": "string",
   "symbol": "string",
   "lastModifiedDateTime": "datetime"
}
```
## See also

[Get Unit of Measure](../api/dynamics_unitofmeasure_get.md)  