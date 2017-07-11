---
title: Shipment Method resource type | Microsoft Docs
description: A Shipment Method.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/11/2017
ms.author: solsen
---

# Shipment method resource type
Represents a method of shipment in Dynamics 365 for Financials, such as UPS, Fedex, and DHL.


## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET shipmentMethod](../api/dynamics_get_shipmentmethods.md)|shipmentMethod|Get a Shipment Method.|
|[POST shipmentMethod](../api/dynamics_create_shipmentmethods.md)|shipmentMethod|Create a Shipment Method.|
|[PATCH shipmentMethod](../api/dynamics_update_shipmentmethods.md)|shipmentMethod|Update a Shipment Method.|
|[DELETE shipmentMethod](../api/dynamics_delete_shipmentmethods.md)|none|Delete a Shipment Method.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the shipmentMethod. Non-editable.|
|code|string|Specifies the shipment method code.|
|displayName|string|Specifies the shipment method display name.|
|lastModifiedDateTime|datetime|The last datetime the shipment method was modified. Read-Only.|  


## Relationships
None

## JSON representation

Here is a JSON representation of the shipmentMethod.

```json
{
  "id": "GUID",
  "code": "string",
  "displayName": "string",
  "lastModifiedDateTime": "datetime"
}

```

## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 
