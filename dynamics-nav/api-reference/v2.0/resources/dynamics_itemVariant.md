---
title: itemVariant resource type | Microsoft Docs
description: A itemVariant object in Dynamics 365 Business Central. 
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# itemVariant resource type
Represents a itemVariant in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)]. You can save the stream as an image directly.

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method                                                       | Return Type |Description                    |
|:-------------------------------------------------------------|:------------|:------------------------------|
|[GET itemVariant](../api/dynamics_itemVariant_get.md)      |itemVariant|Gets a itemVariant object.   |
|[POST itemVariant](../api/dynamics_create_itemVariant.md)  |itemVariant|Creates a itemVariant object.|
|[PATCH itemVariant](../api/dynamics_itemVariant_update.md) |itemVariant|Updates a itemVariant object.|
|[DELETE itemVariant](../api/dynamics_itemVariant_delete.md)|none         |Deletes a itemVariant object.|



## Navigation

| Navigation |Return Type| Description |
|:----------|:----------|:-----------------|
|[item](../resources/dynamics_item.md)|item   |Gets the item of the itemVariant.|

## Properties

| Property                    | Type    | Description                                             |
|:----------------------------|:--------|:--------------------------------------------------------|
| id                          | GUID    | ID of the entity that itemVariant belongs to. Non-editable. |
| width                       | numeric | The itemVariant width.                                      |
| height                      | numeric | The itemVariant height.                                     |
| contentType                 | MIME    | Image type.                                             |
| content@odata.mediaEditLink |         | Link to upload raw image data                           |
| content@odata.mediaReadLink |         | Link to download raw image data                         |

## JSON representation

Here is a JSON representation of the resource.


```json
{
   "id": "GUID",
   "itemId": "GUID",
   "itemNumber": "string",
   "code": "string",
   "description": "string"
}
```

## See also

[Get Picture](../api/dynamics_itemVariant_get.md)  
[Create Picture](../api/dynamics_create_itemVariant.md)  
[Update Picture](../api/dynamics_itemVariant_update.md)  
[Delete Picture](../api/dynamics_itemVariant_delete.md)  