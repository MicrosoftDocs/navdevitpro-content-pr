---
title: Delete picture | Microsoft Docs
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

# Delete picture
Deletes the properties and relationships of a picture object for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request
```
DELETE /businesscentral/companies({id})/items({id2})/picture
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |
|If-Match| [token] Required. When this request header is included and the eTag provided does not match the current tag on the items, the items will not be updated.|

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns `204 No Content` response code. It does not return anything in the response body.

## Example

**Request**

Here is an example of the request. 

```json
DELETE https://api.businesscentral.dynamics.com/v1.0/api/beta/companies({id})/items({id2})/picture
```

**Response**

Here is an example of the response.

```json
HTTP/1.1 204 No Content
```

## See also
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[Picture](../resources/dynamics_picture.md)  
[Get Picture](dynamics_picture_get.md)  
[Update Picture](dynamics_picture_update.md)  
[Post Picture](dynamics_create_picture.md)  
