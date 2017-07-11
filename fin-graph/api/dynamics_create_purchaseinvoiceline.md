---
title: CREATE Purchase Invoice Line method | Microsoft Docs
description: Creates a purchase invoice line.
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

# Create purchase invoice line
Create a purchaseInvoice in Dynamics 365 for Financials.

## HTTP request

```
POST /financials/companies/{id}/purchaseInvoices/{id}/purchaseInvoiceLines
```

## Request headers

|Header|Value|
|------|-----|
|Authorization  |Bearer. Required.    |
|Content-Type  |application/json    |

## Request body
In the request body, supply a JSON representation of a purchaseInvoice object.

## Response
If successful, this method returns ```201 Created``` response code and a purchaseInvoice object in the response body.

## Example

**Request**

Here is an example of a request.

```json
POST https://graph.microsoft.com/beta/financials/companies/{id}/purchaseInvoices/{id}/purchaseInvoiceLines
Content-type: application/json

{
"itemId": "id-value",
"lineType": "Item",
"quantity": 9
}

## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](dynamics_overview.md)