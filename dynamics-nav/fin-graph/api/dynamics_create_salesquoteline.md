---
title: CREATE salesQuoteLine method | Microsoft Docs
description: Creates a sales quote line.
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

# Create salesQuoteLine
Create a salesQuoteLine in Dynamics 365 for Financials.

## HTTP request

```
POST /financials/companies/({id})/salesQuotes/({id})/salesQuoteLines
```

## Request headers

|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required.    |
|Content-Type  |application/json    |

## Request body
In the request body, supply a JSON representation of a salesQuoteLine object.

## Response
If successful, this method returns ```201 Created``` response code and a salesQuoteLine object in the response body.

## Example

**Request**

Here is an example of a request.

```json
POST https://api.financials.dynamics.com/v1.0/api/beta/companies/({id})/salesQuotes/({id})/salesQuoteLines
Content-type: application/json

{
"itemId": "id-value",
"lineType": "Item",
"quantity": 9
}
```

## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md)