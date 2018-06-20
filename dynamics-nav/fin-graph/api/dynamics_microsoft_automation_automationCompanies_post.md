---
title: Create company | Microsoft Docs
description: Create a company in Dynamics 365 Business Central. 
services: 
documentationcenter: ''
author: henrikwh, SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/15/2018
ms.author: henrikwh, SusanneWindfeldPedersen
---


# Create company
Create a company object in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request

```
POST /microsoft/automation/{apiVersion}/companies({companyId})/automationCompanies
```

## Request headers

|Header         |Value                     |
|---------------|--------------------------|
|Authorization  |Bearer {token}. Required. |
|Content-Type   |application/json          |

## Request body
In the request body, supply a JSON representation of a **automationCompany** object.

## Response
If successful, this method returns ```201 Created``` response code and a **automationCompany** object in the response body.

## Example

**Request**

Here is an example of a request.

```json
POST https://api.businesscentral.dynamics.com/v1.0/api/microsoft/automation/beta/companies({id})/automationCompanies
Content-type: application/json

{
    "name": "CRONUS",
    "evaluationCompany": false,
    "displayName": "CRONUS",
    "businessProfileId": ""
}
```




## See Also
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[AutomationCompany entity](../resources/dynamics_microsoft_automation_automationCompany.md)  
[Get automationCompany](../api/dynamics_microsoft_automation_automationCompanies_get.md)  
[Update automationCompany](../api/dynamics_microsoft_automation_automationCompanies_patch.md)  
[Delete automationCompany](../api/dynamics_microsoft_automation_automationCompanies_delete.md)  