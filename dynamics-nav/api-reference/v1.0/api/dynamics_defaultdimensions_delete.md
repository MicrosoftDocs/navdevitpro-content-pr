---
title: Delete defaultDimensions from an entity| Microsoft Docs
description: Deletes the default dimensions of the item in Dynamics 365 Business Central.
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

# Delete defaultDimensions from entities
Deletes the default dimensions of the item in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request
```
DELETE /businesscentral/companies({companyId})/items({itemId})/defaultDimensions({itemId},{dimensionId})
DELETE /businesscentral/companies({companyId})/customers({customerId})/defaultDimensions({customer},{dimensionId})
DELETE /businesscentral/companies({companyId})/employees({employeeId})/defaultDimensions({employeeId},{dimensionId})
DELETE /businesscentral/companies({companyId})/vendors({vendorId})/defaultDimensions({vendorId},{dimensionId})
```

## Request headers

|Header         |Value                     |
|---------------|--------------------------|
|Authorization  |Bearer {token}. Required. |
|If-Match       |Required. When this request header is included and the eTag provided does not match the current tag on the specific entity, the entity will not be updated. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```204 No Content``` response code and it deletes the default dimensions for the entity and corresponding dimension.

## Example

**Request**

Here is an example of the request.

```json
DELETE https://api.businesscentral.dynamics.com/v1.0/api/v1.0/companies({companyId})/items({itemId})/defaultDimensions({itemId},{dimensionId})
```

**Response** 

No Content.

## See also

[defaultDimension resource](../resources/dynamics_defaultDimension.md)  
[Get defaultDimensions](../api/dynamics_defaultdimensions_get.md)  
[Create defaultDimensions](../api/dynamics_defaultdimensions_create.md)  
[Update defaultDimensions](../api/dynamics_defaultdimensions_update.md)  
