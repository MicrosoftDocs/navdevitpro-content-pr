---
title: Delete defaultDimensions Employee | Microsoft Docs
description: Deletes the default dimensions of the employee in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/22/2018
ms.author: solsen
---

# Delete defaultDimensions Employee
Deletes the default dimensions of the employee from [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request
```
DELETE /businesscentral/companies({companyId})/employees({employeeId})/defaultDimensions({employeeId},{dimensionId})
```

## Request headers
|Header         |Value                     |
|---------------|--------------------------|
|Authorization  |Bearer {token}. Required. |
|If-Match       |Required. When this request header is included and the eTag provided does not match the current tag on the **employees**, the **employees** will not be updated. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```204 No Content``` response code and it deletes the default dimensions for the employee and corresponding dimension.

## Example

**Request**

Here is an example of the request.

```json
DELETE https://api.businesscentral.dynamics.com/v1.0/api/beta/companies({companyId})/employees({employeeId})/defaultDimensions({employeeId},{dimensionId})
```

**Response** 

No Content.

## See also
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[Employee](../resources/dynamics_employee.md)  
[Create defaultDimensions Employee](dynamics_employee_create_defaultdimensions.md)  
[Update defaultDimensions Employee](dynamics_employee_update_defaultdimensions.md)  
[Get defaultDimensions Employee](dynamics_employee_get_defaultdimensions.md)  
