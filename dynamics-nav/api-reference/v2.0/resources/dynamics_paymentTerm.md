---
title: paymentTerm resource type | Microsoft Docs
description: A dimension value in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# paymentTerm resource type
Represents a dimension value in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method       | Return Type  |Description                   |
|:-------------|:-------------|:-----------------------------|
|[GET paymentTerm](../api/dynamics_dimensionvalue_get.md)|paymentTerm|Gets a dimension value object.|


## Properties

| Property           | Type                  |Description                                        |
|:-------------------|:----------------------|:--------------------------------------------------|
|id                  |GUID                   |The unique ID of the item.                         |
|code                |string, maximum size 20|The dimension value code.                          |
|displayName         |string                 |Specifies the dimension value's name. This name will appear where the dimension value is used.|
|lastModifiedDateTime|datetime               |The last datetime the dimension value was modified.|  


## JSON representation

Here is a JSON representation of the resource.


```json
{
   "id": "GUID",
   "code": "string",
   "displayName": "string",
   "dueDateCalculation": "string",
   "discountDateCalculation": "string",
   "discountPercent": "decimal",
   "calculateDiscountOnCreditMemos": "boolean",
   "lastModifiedDateTime": "datetime"
}
```

## See also
  
[Get Dimension Value](../api/dynamics_dimensionvalue_get.md)  
