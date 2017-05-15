---
title: VendorPurchases resource type | Microsoft Docs
description: A VendorPurchases.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/03/2017
ms.author: solsen
---

# Vendor Purchases Statement resource type
Represents an vendorPurchases resource type in [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET vendorPurchases](dynamics_get_vendorpurchases.md)|VendorPurchases|Get a VendorPurchases object|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|vendorId|GUID|Represents the vendor ID.|
|vendorNumber|string|Represents the vendor number.|
|name|string|Represents the name of the vendor .|
|totalPurchaseAmount|numeric|Represents the vendor purchases.|
|dateFilter_FilterOnly|date|Represents the date filter for the vendor purchases.|


## Relationships
None

## JSON representation

Here is a JSON representation of the resource.


```json
{
    "vendorId": "GUID",
    "vendorNumber": "string",
    "name": "string",
    "totalPurchaseAmount": "decimal",
    "dateFilter_FilterOnly": "date"
}

```
## See Also
[Graph Reference](dynamics_graph_reference.md)  
