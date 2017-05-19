---
title: DELETE Countries/Regions method | Microsoft Docs
description: Deletes a Countries/Regions.
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

# Delete Countries/Regions Method
Delete a countriesRegions from Dynamics 365 for Financials.

## HTTP request
```
DELETE /financials/companies/{id}/countriesRegions/{id}
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer. Required. |
|If-Match       |Required. When this request header is included and the eTag provided does not match the current tag on the customer, the customer will not be updated. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns ```204 No Content``` response code. It does not return anything in the response body.

## Example

**Request**

Here is an example of the request.

```json
DELETE https://graph.microsoft.com/beta/financials/companies/{id}/countriesRegions/{id}
```

**Response** 

Here is an example of the response. 

```json
HTTP/1.1 204 No Content
```

## See also
[Working with Dynamics 365 for Finance and Operations, Business Edition in Microsoft Graph](../resource_types/dynamics_overview.md) 