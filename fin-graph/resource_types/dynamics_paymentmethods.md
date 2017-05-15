---
title: Payment Method resource type | Microsoft Docs
description: A Payment Method object.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/08/2017
ms.author: solsen
---

# Payment Method resource type
Represents a paymentMethods resource type in [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET paymentMethods](../api/dynamics_get_paymentmethods.md)|paymentMethods|Get a Payment Method.|
|[POST paymentMethods](../api/dynamics_create_paymentmethods.md)|paymentMethods|Create a Payment Method.|
|[PATCH paymentMethods](../api/dynamics_update_paymentmethods.md)|paymentMethods|Update a Payment Method.|
|[DELETE paymentMethods](../api/dynamics_delete_paymentmethods.md)|none|Delete a Payment Method.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the paymentMethods. Read-Only.|
|code|string|Specifies the payment method code. |
|displayName|string|Specifies the payment method display name.|
|lastModifiedDateTime|datetime|The last datetime the payment method was modified. Read-Only.|  


## Relationships
None

## JSON representation

Here is a JSON representation of the paymentMethods.


```json
{
  "id": "GUID",
  "code": "string",
  "displayName": "string",
  "lastModifiedDateTime": "datetime"
}

```

## See Also
[Graph Reference](../api/dynamics_graph_reference.md)  
