---
title: customer payments journal resource type | Microsoft Docs
description: A customer payments journal.
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

# customer payments journal resource type
Represents a customer payments journal in Dynamics 365 for Financials.

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET customer payments journal](../api/dynamics_get_customerpaymentsjournal.md)|customer payments journal|Get customer payments journal.|
|[POST customer payments journal](../api/dynamics_create_customerpaymentsjournal.md)|customer payments journal|Create customer payments journal.|
|[PATCH customer payments journal](../api/dynamics_update_customerpaymentsjournal.md)|customer payments journal|Update customer payments journal.|
|[DELETE customer payments journal](../api/dynamics_delete_customerpaymentsjournal.md)|none|Delete customer payments journal.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the customer payments journal. Non-editable.|
|code|string, maximum size 10| The code of the customer payments journal.|
|displayName|string, maximum size 50| The display name of the customer payments journal.|
|lastModifiedDateTime|datetime|The last datetime the customer payments journal was modified. Read-Only.|

## Relationships

## JSON representation

Here is a JSON representation of the resource.


```json
{
  "id": "GUID",
  "code": "String",
  "displayName": "String",
  "lastModifiedDateTime": "datetime"
}
```

## See also
[Graph Reference](../api/dynamics_graph_reference.md)  
