---
title: picture resource type | Microsoft Docs
description: A picture object in Dynamics 365 Business Central. 
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/16/2018
ms.author: solsen
---

# picture resource type
Represents a picture in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)]. You can save the stream as the image directly.

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md).

## Methods

| Method                                                       | Return Type |Description                    |
|:-------------------------------------------------------------|:------------|:------------------------------|
|[GET picture](../api/dynamics_picture_get.md)      |picture|Gets a picture object.   |
|[POST picture](../api/dynamics_create_picture.md)  |picture|Creates a picture object.|
|[PATCH picture](../api/dynamics_picture_update.md) |picture|Updates a picture object.|
|[DELETE picture](../api/dynamics_picture_delete.md)|none         |Deletes a picture object.|


## Properties
| Property            | Type|Description                                                |
|:----------------------|:----------|:----------------------------------------------------------|
|id          |GUID       |The picture ID. Non-editable.  |
|width        |numeric |The picture width.  |
|height | numeric | The picture height. |
|value| |
|contentType| binary |Image type. |
|@odata.etag||
|@odata.context||
|content@odata.mediaEditLink||
|content@odata.mediaReadLink||


## JSON representation

Here is a JSON representation of the resource.


```json
{
  "@odata.context": "https:\/\/api.businesscentral.dynamics-tie.com\/v1.0\/api\/beta\/$metadata#companies(29a080a9-8dde-4d41-bc50-b9aac6b1ee1b)\/items(07493b2c-d676-4d09-ba8c-fc03607cab76)\/picture",
  "value": [
    {
      "@odata.etag": "W\/\"JzQ0O3J6NzFlMTR5aHBad05uTzgyUEQ1Ujl5ZjkzYVRtM2pTRU1ZQXlNZlAwV3M9MTswMDsn\"",
      "id": "07493b2c-d676-4d09-ba8c-fc03607cab76",
      "width": 516,
      "height": 466,
      "contentType": "image\/png",
      "content@odata.mediaEditLink": "https:\/\/api.businesscentral.dynamics-tie.com\/v1.0\/api\/beta\/companies(29a080a9-8dde-4d41-bc50-b9aac6b1ee1b)\/items(07493b2c-d676-4d09-ba8c-fc03607cab76)\/picture(07493b2c-d676-4d09-ba8c-fc03607cab76)\/content",
      "content@odata.mediaReadLink": "https:\/\/api.businesscentral.dynamics-tie.com\/v1.0\/api\/beta\/companies(29a080a9-8dde-4d41-bc50-b9aac6b1ee1b)\/items(07493b2c-d676-4d09-ba8c-fc03607cab76)\/picture(07493b2c-d676-4d09-ba8c-fc03607cab76)\/content"
    }
  ]
}
```

## See also
[Graph Reference](../api/dynamics_graph_reference.md)  
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[Get Picture](../api/dynamics_picture_get.md)  
[Create Picture](../api/dynamics_create_picture.md)  
[Update Picture](../api/dynamics_picture_update.md)  
[Delete Picture](../api/dynamics_picture_delete.md)  