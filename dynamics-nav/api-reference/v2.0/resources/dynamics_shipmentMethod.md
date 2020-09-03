---
title: shipmentMethod resource type | Microsoft Docs
description: A shipment method in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# shipmentMethod resource type
Represents a shipment method value in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method       | Return Type  |Description                   |
|:-------------|:-------------|:-----------------------------|
|[GET shipmentMethod](../api/dynamics_shipmentMethod_get.md)|shipmentMethod|Gets a Shipment Method object.|


## Properties

| Property           | Type                  |Description                                        |
|:-------------------|:----------------------|:--------------------------------------------------|
|id                  |GUID                   |The unique ID of the item.                         |
|code                |string, maximum size 20|The Shipment Method code.                          |
|displayName         |string                 |Specifies the Shipment Method's name. This name will appear where the Shipment Method is used.|
|lastModifiedDateTime|datetime               |The last datetime the Shipment Method was modified.|  


## JSON representation

Here is a JSON representation of the resource.


```json
{
   "id": "GUID",
   "code": "string",
   "displayName": "string",
   "lastModifiedDateTime": "datetime"
}
```

## See also
  
[Get Shipment Method](../api/dynamics_shipmentMethod_get.md)  
