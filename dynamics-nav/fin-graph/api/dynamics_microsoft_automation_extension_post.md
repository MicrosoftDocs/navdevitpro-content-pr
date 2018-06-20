---
title: Actions on extension | Microsoft Docs
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

# Bound actions on extension
Install and uninstall published extensions in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## Bound Actions

| Actions         | Return Type  |Description|
|:---------------|:-------------|:----------|
|[Microsoft.NAV.install](../api/dynamics_microsoft_automation_extension_post.md)|extension|Installs an published extension.|
|[Microsoft.NAV.uninstall](../api/dynamics_microsoft_automation_extension_post.md)|extension|Uninstalls an extension extensions.|

## HTTP requests

**Install extension**

```json
POST /microsoft/automation/{version}/companies({companyId})//extensions({{extensionId}})/Microsoft.NAV.install
```

**Uninstall extension**

```json
POST /microsoft/automation/{version}/companies({companyId})//extensions({{extensionId}})/Microsoft.NAV.ininstall
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code.

## Example

**Request**

Here is an example of the request.
```json
POST https://api.businesscentral.dynamics.com/v1.0/api/microsoft/automation/beta/companies({companyId})/extensions({extensionId})/Microsoft.NAV.install
```




## See Also
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[Get extensions](../api/dynamics_microsoft_automation_extension_get.md)   
[Install extension](../api/dynamics_microsoft_automation_extension_post.md)  
[Uninstall extension](../api/dynamics_microsoft_automation_extension_post.md)  
[Extension entity](../resources/dynamics_microsoft_automation_extension.md)

