---
title: Get extensions | Microsoft Docs
description: Gets a extension object in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: henrikwh

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/15/2018
ms.author: solsen
---

# Get extension
Retrieve the properties and relationships of an extension object for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request
```
GET /microsoft/automation/{apiVersion}/companies({{companyid}})/extensions
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and list of  **extension** objects in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://api.businesscentral.dynamics.com/v1.0/api/microsoft/automation/beta/companies({id})/extensions
```

**Response**

Here is an example of the response. 

> [!NOTE]  
>   The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
    "packageId": "bf1745d4-2889-49b6-846e-6cb1f6838f45",
    "displayName": "_Exclude_ClientAddIns_",
    "publisher": "Microsoft",
    "versionMajor": 1,
    "versionMinor": 0,
    "isInstalled": true
}
```



## See Also
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[Extension entity](../resources/dynamics_microsoft_automation_extension.md)  
[Install extension](../api/dynamics_microsoft_automation_extension_post.md)  
[Uninstall extension](../api/dynamics_microsoft_automation_extension_post.md)  
