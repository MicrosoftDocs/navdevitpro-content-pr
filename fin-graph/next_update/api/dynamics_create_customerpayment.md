
---
title: CREATE customer payment method | Microsoft Docs
description: Creates a customer payment.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/21/2017
ms.author: solsen
---

# Create customer payment
Creates a customer payment in Dynamics 365 for Financials.

## HTTP request
```
POST /financials/companies/{id}/customerPayments/{id}
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer. Required.    |
|Content-Type  |application/json    |

## Request body
In the request body, supply a JSON representation of customerPayment object.

## Response
If successful, this method returns ```201 Created``` response code and customerPayment object in the response body.

## Example

**Request**

Here is an example of a request.

```json
POST https://graph.microsoft.com/beta/financials/companies/{id}/customerPayment
Content-type: application/json

{
  "lineNumber": 10000,
  "customerId": "customerId-value",
  "customerNumber": "10400",
  "contactId": "contactId-value",
  "postingDate": "2015-12-31",
  "documentNumber": "1234",
  "externalDocumentNumber": "",
  "amount": -1500,
  "appliesToInvoiceId": "appliesToInvoiceId-value",
  "appliesToInvoiceNumber": "100000",
  "description": "",
  "comment": "",
}
```
**Response**

```json
HTTP/1.1 201 Created
Content-type: application/json

{
  "id": "id-value",
  "journalDisplayName": "DEFAULT",
  "lineNumber": 10000,
  "accountId": "id-value",
  "accountNumber": "10400",
  "postingDate": "2015-12-31",
  "documentNumber": "1234",
  "externalDocumentNumber": "",
  "amount": 1500,
  "description": "Accounts Receivable",
  "comment": "",
  "lastModifiedDateTime": "2017-03-17T19:02:22.043Z"
}
```

## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 
