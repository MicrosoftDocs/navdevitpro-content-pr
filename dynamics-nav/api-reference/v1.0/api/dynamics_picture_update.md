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
PATCH /businesscentral/companies({companyId})/items({itemId})/picture({itemId})/content
```

## Request headers

|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |
|Content-Type  |application/octet-stream  | 
|If Match | When this request header is included and the eTag provided does not match the current tag on the picture, the picture will not be updated.|

## Request body
Raw picture binary data.

## Response
If successful, this method returns `204 No Content` response code. It does not return anything in the response body.

## Example

**Request**

Here is an example of the request. 

```json
PATCH https://api.businesscentral.dynamics.com/v1.0/api/beta/companies(companyId)/items(itemId)/picture(itemId)/content
```

**Response**

No response. 

## See also
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[Picture](../resources/dynamics_picture.md)  
[Get Picture](dynamics_picture_get.md)  
[Post Picture](dynamics_create_picture.md)  
[Delete Picture](dynamics_picture_delete.md)  
