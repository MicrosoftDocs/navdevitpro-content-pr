---
title: Create countriesRegions | Microsoft Docs
description: Creates a countries/regions object in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/03/2018
ms.author: solsen
ROBOTS: NOINDEX
---

# Create countriesRegions
Create a countriesRegions object in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request
Replace the URL prefix for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] depending on environment following the [guideline](../../api-reference/v1.0/endpoints-apis-for-dynamics.md).
```
POST businesscentralPrefix/companies({id})/countriesRegions
```
## Request headers

|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |
|Content-Type  |application/json   |

## Request body
In the request body, supply a JSON representation of **countriesRegions** object.

## Response
If successful, this method returns ```201 Created``` response code and a **countriesRegions** object in the response body.

## Example

**Request**

Here is an example of a request.

```json
POST https://{businesscentralPrefix}/api/beta/companies({id})/countriesRegions
Content-type: application/json

{
  "code": "US",
  "displayName": "USA",
  "addressFormat": "City+County+Post Code"
}
```

**Response**

Here is an example of the response. 

> [!NOTE]  
> The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
HTTP/1.1 201 Created
Content-type: application/json

{
  "id": "id-value",
  "code": "US",
  "displayName": "USA",
  "addressFormat": "City+County+Post Code",
  "lastModifiedDateTime": "2017-03-14T15:22:31.753Z"
}
```

## See also
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[Countries Regions](../resources/dynamics_countriesregions.md)  
[Get Countries Regions](dynamics_countriesregions_get.md)  
[Patch Countries Regions](dynamics_countriesregions_update.md)  
[Delete Countries Regions](dynamics_countriesregions_delete.md)  
