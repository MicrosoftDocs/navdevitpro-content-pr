---
title: vendorPurchases resource type | Microsoft Docs
description: A VendorPurchases.
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

# vendorPurchases resource type
Represents a vendor purchase in Dynamics 365 for Financials.

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET vendorPurchases](../api/dynamics_get_vendorpurchases.md)|VendorPurchases|Get a VendorPurchases object|

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
## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 
