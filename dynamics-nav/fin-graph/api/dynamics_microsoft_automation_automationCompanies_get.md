---
title: Get automationCompanies | Microsoft Docs
description: Gets a company object in Dynamics 365 Business Central.
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

# Get automationCompanies
Retrieve the properties and relationships of an automationCompany object for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request
```
GET /microsoft/automation/{apiVersion}/companies({{companyid}})/automationCompanies
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and list of  **automationCompany** objects in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://api.businesscentral.dynamics.com/v1.0/api/microsoft/automation/beta/companies({id})/automationCompanies
```

**Response**

Here is an example of the response. 

> [!NOTE]  
>   The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
    "id": "2b8ea70b-1384-448d-b3d7-1d26c41f3cec",
    "name": "CRONUS Danmark A/S",
    "evaluationCompany": true,
    "displayName": "CRONUS Danmark A/S",
    "businessProfileId": ""
}
```



## See Also
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[automationCompany entity](../resources/dynamics_microsoft_automation_automationCompany.md)  
[Post automationCompany](../api/dynamics_microsoft_automation_automationCompanies_post.md)  
[Update automationCompany](../api/dynamics_microsoft_automation_automationCompanies_patch.md)  
[Delete automationCompany](../api/dynamics_microsoft_automation_automationCompanies_delete.md)  