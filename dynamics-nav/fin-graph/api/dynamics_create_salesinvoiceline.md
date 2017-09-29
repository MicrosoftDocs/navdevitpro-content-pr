---
title: Create salesInvoiceLines | Microsoft Docs
description: Creates a sales invoice line object in Dynamics 365 for Financials. 
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/11/2017
ms.author: solsen
---

# Create salesInvoiceLines
Create a sales invoice line object in Dynamics 365 for Financials.

## HTTP request

```
POST /financials/companies/({id})/salesInvoices/({id})/salesInvoiceLines
```

## Request headers

|Header        |Value                      |
|--------------|---------------------------|
|Authorization |Bearer {token}. Required.  |
|Content-Type  |application/json           |

## Request body
In the request body, supply a JSON representation of a **salesInvoiceLines** object.

## Response
If successful, this method returns ```201 Created``` response code and a **salesInvoiceLines** object in the response body.

## Example

**Request**

Here is an example of a request.

```json
POST https://api.financials.dynamics.com/v1.0/api/beta/companies/({id})/salesInvoices/({id})/salesInvoiceLines
Content-type: application/json

{
"itemId": "id-value",
"lineType": "Item",
"quantity": 9
}
```

## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md)