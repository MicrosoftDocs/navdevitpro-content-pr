---
title: itemCategory resource type | Microsoft Docs
description: An item category in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# itemCategory resource type
Represents an item category in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method       | Return Type  |Description                   |
|:-------------|:-------------|:-----------------------------|
|[GET itemCategory](../api/dynamics_itemCategory_get.md)|itemCategory|Gets a Item Category object.|


## Properties

| Property           | Type                  |Description                                        |
|:-------------------|:----------------------|:--------------------------------------------------|
|id                  |GUID                   |The unique ID of the item.                         |
|code                |string, maximum size 20|The Item Category code.                          |
|displayName         |string                 |Specifies the Item Category's name. This name will appear where the Item Category is used.|
|lastModifiedDateTime|datetime               |The last datetime the Item Category was modified.|  


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
  
[Get Item Category](../api/dynamics_itemCategory_get.md)  
