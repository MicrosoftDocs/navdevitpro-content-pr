---
title: dimension resource type | Microsoft Docs
description: A dimension in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# Dimensions resource type
Represents a dimension in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method       | Return Type  |Description|
|:-------------|:-------------|:----------|
|[GET dimension](../api/dynamics_dimension_get.md)|dimension|Gets a dimension.|



## Navigation

| Navigation |Return Type| Description |
|:----------|:----------|:-----------------|
|[dimensionValues](../resources/dynamics_dimensionvalues.md)|dimensionValues   |Gets the dimensionvalues of the dimension.|



## Properties

| Property           | Type                  |Description               |
|:-------------------|:----------------------|:-------------------------|
|id                  |GUID                   |The unique ID of the item.|
|code                |string, maximum size 20|The dimension code.       |
|displayName         |string                 |Specifies the dimension's name. This name will appear where the dimension is used.|
|lastModifiedDateTime|datetime               |The last datetime the dimension was modified.|  


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
  
[Get Dimensions](../api/dynamics_dimension_get.md)  