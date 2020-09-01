---
title: defaultDimensions resource type | Microsoft Docs
description: A defaultDimensions object in Dynamics 365 Business Central. 
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# defaultDimensions resource type
Represents a defaultDimensions in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)]. You can save the stream as an image directly.

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method                                                       | Return Type |Description                    |
|:-------------------------------------------------------------|:------------|:------------------------------|
|[GET defaultDimensions](../api/dynamics_defaultDimensions_get.md)      |defaultDimensions|Gets a defaultDimensions object.   |
|[POST defaultDimensions](../api/dynamics_create_defaultDimensions.md)  |defaultDimensions|Creates a defaultDimensions object.|
|[PATCH defaultDimensions](../api/dynamics_defaultDimensions_update.md) |defaultDimensions|Updates a defaultDimensions object.|
|[DELETE defaultDimensions](../api/dynamics_defaultDimensions_delete.md)|none         |Deletes a defaultDimensions object.|



## Navigation

| Navigation |Return Type| Description |
|:----------|:----------|:-----------------|
|[item](../resources/dynamics_item.md)|item   |Gets the item of the defaultDimensions.|
|[account](../resources/dynamics_account.md)|account   |Gets the account of the defaultDimensions.|
|[dimension](../resources/dynamics_dimension.md)|dimension   |Gets the dimension of the defaultDimensions.|
|[dimensionValue](../resources/dynamics_dimensionvalue.md)|dimensionValue   |Gets the dimensionvalue of the defaultDimensions.|
|[customer](../resources/dynamics_customer.md)|customer   |Gets the customer of the defaultDimensions.|
|[vendor](../resources/dynamics_vendor.md)|vendor   |Gets the vendor of the defaultDimensions.|
|[employee](../resources/dynamics_employee.md)|employee   |Gets the employee of the defaultDimensions.|

## Properties

| Property                    | Type    | Description                                             |
|:----------------------------|:--------|:--------------------------------------------------------|
| id                          | GUID    | ID of the entity that defaultDimensions belongs to. Non-editable. |
| width                       | numeric | The defaultDimensions width.                                      |
| height                      | numeric | The defaultDimensions height.                                     |
| contentType                 | MIME    | Image type.                                             |
| content@odata.mediaEditLink |         | Link to upload raw image data                           |
| content@odata.mediaReadLink |         | Link to download raw image data                         |

## JSON representation

Here is a JSON representation of the resource.


```json
{
   "parentId": "GUID",
   "dimensionId": "GUID",
   "dimensionCode": "string",
   "dimensionValueId": "GUID",
   "dimensionValueCode": "string",
   "postingValidation": "string"
}
```

## See also

[Get Picture](../api/dynamics_defaultDimensions_get.md)  
[Create Picture](../api/dynamics_create_defaultDimensions.md)  
[Update Picture](../api/dynamics_defaultDimensions_update.md)  
[Delete Picture](../api/dynamics_defaultDimensions_delete.md)  