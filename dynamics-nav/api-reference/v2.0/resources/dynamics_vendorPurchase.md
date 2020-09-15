---
title: vendorPurchase resource type | Microsoft Docs
description: A vendor purchase object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/15/2020
ms.author: solsen
---

# vendorPurchase resource type
Represents an vendor purchase in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method              | Return Type|Description               |
|:--------------------|:-----------|:-------------------------|
|[GET vendorPurchase](../api/dynamics_vendorPurchase_Get.md)|vendorPurchase|Gets a vendor purchase object.|
|[DELETE vendorPurchase](../api/dynamics_vendorPurchase_Delete.md)|vendorPurchase|Deletes a vendor purchase object.|
|[POST vendorPurchase](../api/dynamics_vendorPurchase_Create.md)|vendorPurchase|Creates a vendor purchase object.|
|[PATCH vendorPurchase](../api/dynamics_vendorPurchase_Update.md)|vendorPurchase|Updates a vendor purchase object.|






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
[DELETE vendorPurchase](../api/dynamics_vendorPurchase_Delete.md)
[POST vendorPurchase](../api/dynamics_vendorPurchase_Create.md)
[PATCH vendorPurchase](../api/dynamics_vendorPurchase_Update.md)

