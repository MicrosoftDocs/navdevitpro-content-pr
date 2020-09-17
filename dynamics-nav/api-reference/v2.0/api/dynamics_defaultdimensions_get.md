---
title: Get defaultDimensions for an entity | Microsoft Docs
description: Gets an item default dimensions in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/01/2019
ms.author: solsen
---

# Get entity defaultDimensions
Gets the default dimensions of an entity in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request
Replace the URL prefix for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] depending on environment following the [guideline](../../v2.0/endpoints-apis-for-dynamics.md). 
The following example gets the default dimensions of an entity.

```
GET businesscentralPrefix/companies({companyId})/items({itemId})/defaultDimensions
GET businesscentralPrefix/companies({companyId})/customers({customerId})/defaultDimensions
GET businesscentralPrefix/companies({companyId})/vendors({vendorId})/defaultDimensions
GET businesscentralPrefix/companies({companyId})/employees({emplyeeId})/defaultDimensions
```
## Request header

|Header|Value|
|------|-----|
|Authorization| Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response 

If successful, this method returns a `200 OK` response code and the **default dimensions** in the response body.

## Example 
**Request**

```json
GET https://{businesscentralPrefix}/api/v2.0/companies({companyId})/items({itemId})/defaultDimensions
```

**Response**  
Here is an example of the response.

> [!NOTE]  
> The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
    "id": "5b049aad-bde4-ea11-bbf2-00155df3a615",
    "parentId": "53049aad-bde4-ea11-bbf2-00155df3a615",
    "dimensionId": "47c99ea7-bde4-ea11-bbf2-00155df3a615",
    "dimensionCode": "DEPARTMENT",
    "dimensionValueId": "49c99ea7-bde4-ea11-bbf2-00155df3a615",
    "dimensionValueCode": "SALES",
    "postingValidation": " "
} 
```

## See also
[Tips for working with the APIs](/dynamics365/business-central/dev-itpro/developer/devenv-connect-apps-tips)  
[defaultDimension resource](../resources/dynamics_defaultDimension.md)  
[Create defaultDimensions](../api/dynamics_defaultdimensions_create.md)  
[Update defaultDimensions](../api/dynamics_defaultdimensions_update.md)  
[Delete defaultDimensions](../api/dynamics_defaultdimensions_delete.md)  

