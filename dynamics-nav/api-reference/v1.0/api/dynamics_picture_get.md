---
title: Get picture | Microsoft Docs
description: A picture object in Dynamics 365 Business Central. 
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/01/2019
ms.author: solsen
---

# Get picture
Retrieve the properties and relationships of a picture object for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request
Replace the URL prefix for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] depending on environment following the [guideline](../../v1.0/endpoints-apis-for-dynamics.md).s
```
GET businesscentralPrefix/companies({companyId})/items({itemId})/picture
GET businesscentralPrefix/companies({companyId})/employee({employeeId})/picture
GET businesscentralPrefix/companies({companyId})/vendor({vendorId})/picture
GET businesscentralPrefix/companies({companyId})/customer({customerId})/picture

```

## Request headers

|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |

## Response
If successful, this method returns a ```200 OK``` response code and a **picture** object in the response body.

## Example

**Request**

Here is an example of the request. 

**GET Metadata** 

```json
GET https://{businesscentralPrefix}/api/v1.0/companies(companyId)/items(itemId)/picture(itemId)
```
**Response**

Here is an example of the response.

> [!NOTE]  
> The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
  "id": "d0e5d5da-795a-4924-b376-13665f794cdd",
  "width": 500,
  "height": 496,
  "contentType": "image\jpeg",
  "content@odata.mediaEditLink": "https:\\api.businesscentral.dynamics-tie.com\v1.0\api\beta\companies(55c438d0-2f5c-44a0-9965-20b4923d0bef)\items(d0e5d5da-795a-4924-b376-13665f794cdd)\picture(d0e5d5da-795a-4924-b376-13665f794cdd)\content",
  "content@odata.mediaReadLink": "https:\\api.businesscentral.dynamics-tie.com\v1.0\api\beta\companies(55c438d0-2f5c-44a0-9965-20b4923d0bef)\items(d0e5d5da-795a-4924-b376-13665f794cdd)\picture(d0e5d5da-795a-4924-b376-13665f794cdd)\content"
}
```

**GET Content**

```json
GET https://{businesscentralPrefix}/api/v1.0/companies(companyId)/items(itemId)/picture(itemId)/content
```

**Response**

Body is the raw image data. 


## See also
[Tips for working with the APIs](/dynamics365/business-central/dev-itpro/developer/devenv-connect-apps-tips)  



[Error Codes](../dynamics_error_codes.md)  



[Error Codes](../dynamics_error_codes.md)  
[Picture](../resources/dynamics_picture.md)  
[Create Picture](dynamics_create_picture.md)  
[Update Picture](dynamics_picture_update.md)  
[Delete Picture](dynamics_picture_delete.md)  
