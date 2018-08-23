---
title: Delete vendor defaultDimensions | Microsoft Docs
description: Deletes the default dimensions of the vendor in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/22/2018
ms.author: solsen
---

# Delete vendor defaultDimensions
Deletes the default dimensions of the vendor from [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request
```
DELETE /businesscentral/companies({companyId})/vendors({vendorId})/defaultDimensions({vendorId},{dimensionId})
```

## Request headers
|Header         |Value                     |
|---------------|--------------------------|
|Authorization  |Bearer {token}. Required. |
|If-Match       |Required. When this request header is included and the eTag provided does not match the current tag on the **vendors**, the **vendors** will not be updated. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```204 No Content``` response code and it deletes the default dimensions for the vendor and corresponding dimension.

## Example

**Request**

Here is an example of the request.

```json
DELETE https://api.businesscentral.dynamics.com/v1.0/api/beta/companies({companyId})/vendors({vendorId})/defaultDimensions({vendorId},{dimensionId})
```

**Response** 

No Content.

## See also
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[Vendor](../resources/dynamics_vendor.md)  
[Create defaultDimensions Vendor](dynamics_vendor_create_defaultdimensions.md)  
[Update defaultDimensions Vendor](dynamics_vendor_update_defaultdimensions.md)  
[Get defaultDimensions Vendor](dynamics_vendor_get_defaultdimensions.md)  
