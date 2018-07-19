---
title: Update picture | Microsoft Docs
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

# Update picture
Updates the properties and relationships of a picture object for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request
```
PATCH /businesscentral/companies({id})/items({id2})/picture({id2})/content
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |
|Content-Type  |application/octet-stream  | 
|If-Match| [token] Required. When this request header is included and the eTag provided does not match the current tag on the items, the items will not be updated.|

## Request body
In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

> [!NOTE]  
> Body should be raw binary of the file.

## Response
If successful, this method returns a ```200 OK``` response code and a **picture** object in the response body.

## Example

**Request**

Here is an example of the request. 

```json
PATCH https://api.businesscentral.dynamics.com/v1.0/api/beta/companies({id})/items({id2})/picture({id2})/content
```

**Response**

Here is an example of the response.

> [!NOTE]  
> The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

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
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[Picture](../resources/dynamics_picture.md)  
[Get Picture](dynamics_picture_get.md)  
[Post Picture](dynamics_create_picture.md)  
[Delete Picture](dynamics_picture_delete.md)  
