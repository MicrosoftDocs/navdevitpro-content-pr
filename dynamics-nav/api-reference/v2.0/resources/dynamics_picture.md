---
title: picture resource type | Microsoft Docs
description: A picture object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/15/2020
ms.author: solsen
---

# picture resource type
Represents an picture in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method              | Return Type|Description               |
|:--------------------|:-----------|:-------------------------|
|[GET picture](../api/dynamics_picture_Get.md)|picture|Gets a picture object.|
|[DELETE picture](../api/dynamics_picture_Delete.md)|picture|Deletes a picture object.|
|[POST picture](../api/dynamics_picture_Create.md)|picture|Creates a picture object.|
|[PATCH picture](../api/dynamics_picture_Update.md)|picture|Updates a picture object.|




## Navigation

| Navigation |Return Type| Description |    
|:----------|:----------|:-----------------|
|[item](../resources/dynamics_item.md)|item |Gets the item of the picture.|
|[customer](../resources/dynamics_customer.md)|customer |Gets the customer of the picture.|
|[vendor](../resources/dynamics_vendor.md)|vendor |Gets the vendor of the picture.|
|[employee](../resources/dynamics_employee.md)|employee |Gets the employee of the picture.|



## Navigation

| Navigation |Return Type| Description |
|:----------|:----------|:-----------------|
|[item](../resources/dynamics_item.md)|item   |Gets the item of the picture.|
|[customer](../resources/dynamics_customer.md)|customer   |Gets the customer of the picture.|
|[vendor](../resources/dynamics_vendor.md)|vendor   |Gets the vendor of the picture.|
|[employee](../resources/dynamics_employee.md)|employee   |Gets the employee of the picture.|



## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|id|GUID|The unique ID of the item. Non-editable.|
|width|integer|The width of the picture.|
|height|integer|The height of the picture.|
|contentType|string|The media type of the picture.|
|content|stream|The picture's content.|


## JSON representation

Here is a JSON representation of the picture resource.


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

[GET picture](../api/dynamics_picture_Get.md)
[DELETE picture](../api/dynamics_picture_Delete.md)
[POST picture](../api/dynamics_picture_Create.md)
[PATCH picture](../api/dynamics_picture_Update.md)

