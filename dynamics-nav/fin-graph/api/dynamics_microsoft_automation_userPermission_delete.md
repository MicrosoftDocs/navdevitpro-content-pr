---
title: Delete userPermission | Microsoft Docs
description: Delete userPermission objects in Dynamics 365 Business Central.
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

# Delete userPermission
Removes a user from userPermission object for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request

```json
DELETE /microsoft/automation/{apiVersion}/companies({companyId})/users({userSecurityID})/userPermissions({userSecurityID},'{id}',{companyName}','{scope}',{appId})

```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |
|If-Match|*|
## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```204 No Content``` response code.

## Example

**Request**

Here is an example of the request.
```json
DELETE https://api.businesscentral.dynamics.com/v1.0/api/microsoft/automation/beta/companies({companyId})/users({userSecurityId})/userPermissions(781f5ae5-a5d9-4ec3-8cea-2167a8064dc6, 'SECURITY', 'CRONOS','System',00000000-0000-0000-0000-000000000000)
If-Match:*
```

## See Also
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[UserPermission entity](../resources/microsoft/automation/dynamics_userPermission.md)  
