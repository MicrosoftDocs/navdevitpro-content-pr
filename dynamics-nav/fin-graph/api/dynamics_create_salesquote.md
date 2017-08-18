---
title: CREATE Sales Quote method | Microsoft Docs
description: Creates a sales quote.
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

# Create sales quote
Create a salesQuote in Dynamics 365 for Financials.

## HTTP request

```
POST /financials/companies/{id}/salesQuotes
```

## Request headers

|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required.    |
|Content-Type  |application/json    |

## Request body
In the request body, supply a JSON representation of a salesQuote object.

## Response
If successful, this method returns ```201 Created``` response code and a salesQuote object in the response body.

## Example

**Request**

Here is an example of a request.

```json
POST https://api.financials.dynamics.com/v1.0/api/beta/companies/{id}/salesQuotes
Content-type: application/json

{
  "id": "id-value",
  "number": "1006",
  "documentDate": "2016-12-31",
  "customerNumber": "10000",
  "currencyCode": "GBP",
  "paymentTerms": "COD"
}
```

## See also  
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md)  
