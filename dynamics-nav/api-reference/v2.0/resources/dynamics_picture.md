---
title: picture resource type | Microsoft Docs
description: A picture object in Dynamics 365 Business Central. 
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# picture resource type
Represents a picture in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)]. You can save the stream as an image directly.

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method                                                       | Return Type |Description                    |
|:-------------------------------------------------------------|:------------|:------------------------------|
|[GET picture](../api/dynamics_picture_get.md)      |picture|Gets a picture object.   |
|[POST picture](../api/dynamics_create_picture.md)  |picture|Creates a picture object.|
|[PATCH picture](../api/dynamics_picture_update.md) |picture|Updates a picture object.|
|[DELETE picture](../api/dynamics_picture_delete.md)|none         |Deletes a picture object.|



## Navigation

| Navigation |Return Type| Description |
|:----------|:----------|:-----------------|
|[item](../resources/dynamics_item.md)|item   |Gets the item of the picture.|
|[customer](../resources/dynamics_customer.md)|customer   |Gets the customer of the picture.|
|[vendor](../resources/dynamics_vendor.md)|vendor   |Gets the vendor of the picture.|
|[employee](../resources/dynamics_employee.md)|employee   |Gets the employee of the picture.|



## Properties

| Property                    | Type    | Description                                             |
|:----------------------------|:--------|:--------------------------------------------------------|
| id                          | GUID    | ID of the entity that picture belongs to. Non-editable. |
| width                       | numeric | The picture width.                                      |
| height                      | numeric | The picture height.                                     |
| contentType                 | MIME    | Image type.                                             |
| content@odata.mediaEditLink |         | Link to upload raw image data                           |
| content@odata.mediaReadLink |         | Link to download raw image data                         |

## JSON representation

Here is a JSON representation of the resource.


```json
{
   "id": "GUID",
   "width": "integer",
   "height": "integer",
   "contentType": "string",
   "content": "stream"
}
```

## See also

[Get Picture](../api/dynamics_picture_get.md)  
[Create Picture](../api/dynamics_create_picture.md)  
[Update Picture](../api/dynamics_picture_update.md)  
[Delete Picture](../api/dynamics_picture_delete.md)  