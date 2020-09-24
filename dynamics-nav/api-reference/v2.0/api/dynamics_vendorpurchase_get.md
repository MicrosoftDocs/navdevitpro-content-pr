---
title: GET vendorPurchases | Microsoft Docs
description: Gets a vendorPurchase object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/01/2020
ms.author: solsen
---

# vendorPurchases resource type
Represents a vendor purchase in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET vendorPurchases](../api/dynamics_vendorpurchases_get.md)|vendorPurchases|Gets a vendor purchase object.|

## Properties

| Property     | Type   |Description|
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
[Tips for working with the APIs](/dynamics365/business-central/dev-itpro/developer/devenv-connect-apps-tips)  
[vendorPurchase](../resources/dynamics_vendorPurchase.md)  
<!--links-->
