---
title: Create customerPaymentsJournals | Microsoft Docs
description: Creates a customer payments journal object in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/04/2019
ms.author: solsen
---

# Create customerPaymentsJournals
Creates a customer payments journal object in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request
Replace the URL prefix for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] depending on environment following the [guideline](../../v2.0/endpoints-apis-for-dynamics.md).

```
POST businesscentralPrefix/companies({id})/customerPaymentJournals({id})
```

## Request headers

|Header        |Value                    |
|--------------|-------------------------|
|Authorization |Bearer {token}. Required.|
|Content-Type  |application/json         |

## Request body
In the request body, supply a JSON representation of **customerPaymentJournals** object.

## Response
If successful, this method returns ```201 Created``` response code and a **customerPaymentJournals** object in the response body.

## Example

**Request**

Here is an example of a request.

```json
POST https://{businesscentralPrefix}/api/v2.0/companies({id})/customerPaymentJournals
Content-type: application/json
```json
{
  "code": "DEFAULT"
}
```

**Response**

```json
HTTP/1.1 201 Created
Content-type: application/json

{
    "id": "dc1b6a90-44e3-ea11-bb43-000d3a2feca1",
    "code": "GENERAL",
    "displayName": "GENERAL",
    "lastModifiedDateTime": "2020-08-21T00:24:35.687Z",
    "balancingAccountId": "00000000-0000-0000-0000-000000000000",
    "balancingAccountNumber": "10100"
}
```

## See also
[Tips for working with the APIs](/dynamics365/business-central/dev-itpro/developer/devenv-connect-apps-tips)  
[Microsoft Graph Reference](../api/dynamics_graph_reference.md)   
[Customer Payments Journal](../resources/dynamics_customerpaymentsjournal.md)  
[Get Customer Payments Journal](dynamics_customerpaymentsjournal_get.md)  
[Patch Customer Payments Journal](dynamics_customerpaymentsjournal_update.md)  
[Delete Customer Payments Journal](dynamics_customerpaymentsjournal_delete.md)  