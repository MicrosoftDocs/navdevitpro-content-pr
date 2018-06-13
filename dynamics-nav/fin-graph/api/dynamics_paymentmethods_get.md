---
title: Get paymentMethods | Microsoft Docs
description: Gets a payment method object in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/19/2018
ms.author: solsen
---

# Get paymentMethods
Retrieve the properties and relationships of a payment method object for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request

```
GET /businesscentral/companies({id})/paymentMethods({id})
```

## Request headers
|Header         |Value                     |
|---------------|--------------------------|
|Authorization  |Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and a **paymentMethods** object in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://api.businesscentral.dynamics.com/v1.0/api/beta/companies({id})/paymentMethods({id})
```

**Response**

Here is an example of the response. 

> [!NOTE]  
>   The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{

  "id": "id-value",
  "code": "CHECK",
  "displayName": "Check payment",
  "lastModifiedDateTime": "2017-03-22T08:35:48.33Z"
}
```


## See also
[Graph Reference](../api/dynamics_graph_reference.md)  
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[Payment Methods](../resources/dynamics_paymentmethods.md)  
[Create Payment Methods](../api/dynamics_create_paymentmethods.md)  
[Update Payment Methods](../api/dynamics_paymentmethods_update.md)  
[Delete Payment Methods](../api/dynamics_paymentmethods_delete.md)  