---
title: shipmentMethod resource type | Microsoft Docs
description: A shipment method object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/22/2020
ms.author: solsen
---

# shipmentMethod resource type
Represents a shipment method in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods
| Method | Return Type|Description |
|:--------------------|:-----------|:-------------------------|
|[GET shipmentMethod](../api/dynamics_shipmentMethod_Get.md)|shipmentMethod|Gets a shipment method object.|
|[DELETE shipmentMethod](../api/dynamics_shipmentMethod_Delete.md)|none|Deletes a shipment method object.|
|[POST shipmentMethod](../api/dynamics_shipmentMethod_Create.md)|shipmentMethod|Creates a shipment method object.|
|[PATCH shipmentMethod](../api/dynamics_shipmentMethod_Update.md)|shipmentMethod|Updates a shipment method object.|






## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|id|GUID|The unique ID of the item. Non-editable.|
|code|string|The code of the shipment method.|
|displayName|string|Specifies the shipment method's name. This name will appear on all sales documents for the shipment method.|
|lastModifiedDateTime|datetime|The last datetime the shipment method was modified. Read-Only.|


## JSON representation

Here is a JSON representation of the shipmentMethod resource.


```json
{
   "id": "GUID",
   "code": "string",
   "displayName": "string",
   "lastModifiedDateTime": "datetime"
}
```
## See also

[GET shipmentMethod](../api/dynamics_shipmentMethod_Get.md)
[DELETE shipmentMethod](../api/dynamics_shipmentMethod_Delete.md)
[POST shipmentMethod](../api/dynamics_shipmentMethod_Create.md)
[PATCH shipmentMethod](../api/dynamics_shipmentMethod_Update.md)

