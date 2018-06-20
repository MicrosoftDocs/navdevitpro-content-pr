---
title: Patch configurationPackage | Microsoft Docs
description: Gets a configurationPackage object in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: henrikwh, SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/19/2018
ms.author: henrikwh, solsen
---

# Patch configurationPackage
Uploads a RapidStart package to the configurationPackage object for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP requests

### Upload RapidStart package

```json
PATCH /microsoft/automation/{apiVersion}/companies({companyId})/configurationPackages('{packageName}')/file('{packageName}')/content
Content-type: application/octet-stream
{
    FILE
}
```


## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |
|Content-type|application/octet-stream|
|If-Match|*|

## Request body
Content of the requestbody is a RapidStart package.

## Response
If successful, this method returns a ```204 No Content```.

## Example

**Request**

Here is an example of the request.
```json
PATCH https://api.businesscentral.dynamics.com/v1.0/api/microsoft/automation/beta/companies({companyId})//configurationPackages('{packageName}')/file('{packageName}')/content
Authorization : Bearer {token}
Content-type : application/octet-stream
If-Match:-*
{
    FILE
}
```

## See Also
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[ConfigurationPackages entity](../resources/microsoft/automation/dynamics_configurationPackages.md)  
