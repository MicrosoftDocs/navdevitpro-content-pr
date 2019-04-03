---
title: Create picture | Microsoft Docs
description: A picture object in Dynamics 365 Business Central. 
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/01/2019
ms.author: solsen
---

# Create picture
Creates the properties and relationships of a picture object for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request
```
POST /businesscentral/companies({companyId})/items({itemId})/picture({pictureId})/content
POST /businesscentral/companies({companyId})/vendors({vendorId})/picture({pictureId})/content
POST /businesscentral/companies({companyId})/employees({employeeId})/picture({pictureId})/content
POST /businesscentral/companies({companyId})/customers({customerId})/picture({pictureId})/content
```

## Request headers

|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |
|Content-Type | application/octet-stream |


## Request body
Raw picture binary data.

## Response
If successful, this method returns a `204 No Content` response code. It does not return anything in the response body.

## Example

**Request**

Here is an example of the request. 

```json
POST https://api.businesscentral.dynamics.com/v1.0/api/v1.0/companies(companyId)/items(itemId)/picture(itemId)/content
```

**Response**

No content.

## See also



[Error Codes](../dynamics_error_codes.md)  



[Error Codes](../dynamics_error_codes.md)  
[Picture](../resources/dynamics_picture.md)  
[Get Picture](dynamics_picture_get.md)  
[Update Picture](dynamics_picture_update.md)  
[Delete Picture](dynamics_picture_delete.md)  