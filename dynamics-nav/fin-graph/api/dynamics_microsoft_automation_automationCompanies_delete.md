---
title: Delete a company | Microsoft Docs
description: Deletes a company object in Dynamics 365 Business Central.
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

# Delete companies
Retrieve the properties and relationships of an automationCompany object for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request
```
DELETE /microsoft/automation/{apiVersion}/companies({companyID})/automationCompanies({companyIDToBeDeleted})
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns ```204 No Content``` response code. It does not return anything in the response body.

## Example

**Request**

Here is an example of the request.
```json
DELETE https://api.businesscentral.dynamics.com/v1.0/api/microsoft/automation/beta/companies({id})/automationCompanies({{companyIDToBeDeleted}})
```

**Response**

Here is an example of the response. 
```json
HTTP/1.1 204 No Content
```


## See Also
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[AutomationCompany entity](../resources/dynamics_microsoft_automation_automationCompany.md)  
[Get automationCompany](../api/dynamics_microsoft_automation_automationCompanies_get.md)  
[Post automationCompany](../api/dynamics_microsoft_automation_automationCompanies_post.md)  
[Update automationCompany](../api/dynamics_microsoft_automation_automationCompanies_patch.md)  
