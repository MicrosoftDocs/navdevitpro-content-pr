---
title: DELETE employee method | Microsoft Docs
description: Deletes an employee.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/13/2017
ms.author: solsen
---

# Delete employee
Delete an employee from Dynamics 365 for Financials.

## HTTP request
```
DELETE /financials/companies/{id}/employees/{id}
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer. Required. |
|If-Match       |Required. When this request header is included and the eTag provided does not match the current tag on the employee, the employee will not be updated. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns ```204 No Content``` response code. It does not return anything in the response body.

## Example

**Request**

Here is an example of the request.

```json
DELETE https://graph.microsoft.com/beta/financials/companies/{id}/employees/{id}
```

**Response** 

Here is an example of the response. 

```json
HTTP/1.1 204 No Content
```



## See also
[Working with Dynamics 365 for Finance and Operations, Business Edition in Microsoft Graph](../resources/dynamics_overview.md) 
