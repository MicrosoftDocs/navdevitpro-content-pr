---
title: paymentMethod resource type | Microsoft Docs
description: A payment method object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/01/2020
ms.author: solsen
---

# paymentMethod resource type
Represents a payment method in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods
| Method | Return Type|Description |
|:--------------------|:-----------|:-------------------------|
|[GET paymentMethod](../api/dynamics_paymentMethod_Get.md)|paymentMethod|Gets a payment method object.|
|[DELETE paymentMethod](../api/dynamics_paymentMethod_Delete.md)|none|Deletes a payment method object.|
|[POST paymentMethod](../api/dynamics_paymentMethod_Create.md)|paymentMethod|Creates a payment method object.|
|[PATCH paymentMethod](../api/dynamics_paymentMethod_Update.md)|paymentMethod|Updates a payment method object.|






## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|id|GUID|The unique ID of the item. Non-editable.|
|code|string|The code of the payment method.|
|displayName|string|Specifies the payment method's name. This name will appear on all sales documents for the payment method.|
|lastModifiedDateTime|datetime|The last datetime the payment method was modified. Read-Only.|


## JSON representation

Here is a JSON representation of the paymentMethod resource.


```json
{
   "id": "GUID",
   "code": "string",
   "displayName": "string",
   "lastModifiedDateTime": "datetime"
}
```
## See also

[GET paymentMethod](../api/dynamics_paymentMethod_Get.md)   
[DELETE paymentMethod](../api/dynamics_paymentMethod_Delete.md)   
[POST paymentMethod](../api/dynamics_paymentMethod_Create.md)   
[PATCH paymentMethod](../api/dynamics_paymentMethod_Update.md)   

