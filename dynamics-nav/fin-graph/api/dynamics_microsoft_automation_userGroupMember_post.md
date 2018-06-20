---
title: Post userGroupMembers | Microsoft Docs
description: Adds a user to userGroupMember objects in Dynamics 365 Business Central.
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

# post userGroupMembers
Adds user to a userGroupMembers object for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request

```json
POST /microsoft/automation/{apiVersion}/companies({companyId})/users({userSecurityID})/userGroupMembers
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```201 Created``` response code and a  **userGroupMembers** object in the response body.

## Example

**Request**

Here is an example of the request.
```json
POST https://api.businesscentral.dynamics.com/v1.0/api/microsoft/automation/beta/companies({companyId})/users({userSecurityID})/userGroupMembers
Content-Type:application/json
{ 
    "code": "D365 EXT. ACCOUNTANT", 
    "companyName" : "CRONUS Danmark A/S"
}
```

**Response**

Here is an example of the response.

> [!NOTE]  
>   The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
    "code": "D365 EXT. ACCOUNTANT",
    "userSecurityID": "5bb78dd8-9b40-4fc5-bc79-a28918f9d70e",
    "companyName": "CRONUS Danmark A/S",
    "displayName": ""
}
```

## See Also
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[UserGroupMembers entity](../resources/dynamics_microsoft_automation_userGroupMember.md)  
