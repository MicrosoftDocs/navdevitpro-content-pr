---
title: Get customerPaymentsJournals | Microsoft Docs
description: Gets a customer payment journal in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/01/2019
ms.author: solsen
---

# Get customerPaymentsJournals
Retrieve the properties and relationships of a customer payment journal object for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request

```
GET /businesscentral/companies({id})/customerPaymentsJournals({id})
```

## Request headers

|Header       |Value                     |
|-------------|--------------------------|
|Authorization|Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and a **customerPaymentsJournals** object in the response body.

## Example

**Request**

Here is an example of the request.

```json
GET https://api.businesscentral.dynamics.com/v1.0/api/v1.0/companies({id})/customerPaymentsJournals({id})
```

**Response**

Here is an example of the response. 

> [!NOTE]  
>   The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
  "id": "id-value",
  "code": "DEFAULT",
  "displayName": "Default Journal Batch",
  "lastModifiedDateTime": "2017-05-17T11:30:01.313Z"
}
```

## See also
[Microsoft Graph Reference](../api/dynamics_graph_reference.md)  



[Error Codes](../dynamics_error_codes.md)  
[Customer Payments Journal](../resources/dynamics_customerpaymentsjournal.md)  
[Get Customer Payments Journal](dynamics_customerpaymentsjournal_get.md)  
[Patch Customer Payments Journal](dynamics_customerpaymentsjournal_update.md)  
[Delete Customer Payments Journal](dynamics_customerpaymentsjournal_delete.md)  
