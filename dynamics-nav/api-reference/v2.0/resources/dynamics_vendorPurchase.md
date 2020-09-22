---
title: vendorPurchase resource type | Microsoft Docs
description: A vendor purchase object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/22/2020
ms.author: solsen
---

# vendorPurchase resource type
Represents a vendor purchase in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods
| Method | Return Type|Description |
|:--------------------|:-----------|:-------------------------|
|[GET vendorPurchase](../api/dynamics_vendorPurchase_Get.md)|vendorPurchase|Gets a vendor purchase object.|






## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|vendorId|GUID|The unique ID of vendor.|
|vendorNumber|string|Specifies vendor's number.|
|name|string|Represents the vendor purchase's name.|
|totalPurchaseAmount|decimal|Represents the vendor purchases.|
|dateFilter_FilterOnly|date|Represents the date filter for the vendor purchase.|


## JSON representation

Here is a JSON representation of the vendorPurchase resource.


```json
{
   "vendorId": "GUID",
   "vendorNumber": "string",
   "name": "string",
   "totalPurchaseAmount": "decimal",
   "dateFilter_FilterOnly": "date"
}
```
## See also

[GET vendorPurchase](../api/dynamics_vendorPurchase_Get.md)

