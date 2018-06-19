---
title: Get userGroupMembers | Microsoft Docs
description: Gets  userGroupMember objects in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: henrikwh, SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/15/2018
ms.author: henrikwh, solsen
---

# Get userGroupMembers
Retrieve the properties and relationships of an userGroupMembers object for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request
```
GET /microsoft/automation/{apiVersion}/companies({companyId})/users({userSecurityID})/userGroupMembers
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and list of  **userGroupMembers** objects in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://api.businesscentral.dynamics.com/v1.0/api/microsoft/automation/beta/companies({companyId})/users({userSecurityID})/userGroupMembers
```

**Response**

Here is an example of the response. 

> [!NOTE]  
>   The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
    "code": "D365 BUS PREMIUM",
    "userSecurityID": "5bb78dd8-9b40-4fc5-bc79-a28918f9d70e",
    "companyName": "CRONUS Danmark A/S",
    "displayName": "D365 Premium Business-adgang"
}
```

## See Also
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[UserGroupMembers entity](../resources/microsoft/automation/dynamics_userGroupMembers.md)  
