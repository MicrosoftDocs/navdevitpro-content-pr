---
title: countryRegion resource type | Microsoft Docs
description: A countryRegion object in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# countryRegion resource type
Represents an countryRegion object in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method       | Return Type  |Description|
|:-------------|:-------------|:----------|
|[GET countryRegion](../api/dynamics_countryRegion_get.md)|countryRegion|Get a countryRegion object.|

## Properties

| Property     | Type   |Description                              |
|:-------------|:-------|:----------------------------------------|
|lineNumber    |numeric |The countryRegion item line number.  |
|display       |string  |The countryRegion item display name. |
|netChange     |numeric |The countryRegion item Net Change.   |
|lineType      |string  |The countryRegion item line type can be: header, detail, total, or spacer.|
|indentation   |numeric |The countryRegion item indentation used in report layout.|
|dateFilter    |date    |The date filter used to calculate the countryRegion items.|


## JSON representation

Here is a JSON representation of the resource.


```json
{
   "id": "GUID",
   "code": "string",
   "displayName": "string",
   "addressFormat": "string",
   "lastModifiedDateTime": "datetime"
}
```
## See also
  
[Get countryRegion](../api/dynamics_countryRegion_get.md)  
[Balance Sheet](dynamics_balancesheet.md)  
