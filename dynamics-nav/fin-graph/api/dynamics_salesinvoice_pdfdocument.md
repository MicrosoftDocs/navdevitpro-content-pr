---
title: Get pdfDocument | Microsoft Docs
description: Gets a PDF document on a salesInvoice in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/13/2018
ms.author: solsen
---

# Get pdfDocument
Retrieve a PDF print-out of the corresponding document as binary content for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].


## HTTP request
The following example gets a link to the content of the PDF:

```
GET /businesscentral/api/beta/companies({id})/salesInvoices({id})/pdfDocument
```
The following example gets the content, the actual PDF file in binary format:

```
GET /businesscentral/api/beta/companies({id})/salesInvoices({id})/pdfDocument/content
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and a ??? in the response body.

## Example

**Request**
Here is an example of the request.
```json
GET https://api.businesscentral.dynamics.com/v1.0/api/beta/companies({id})/salesInvoices({id})/pdfDocument
```

**Response**
Here is an example of the response.

> [!NOTE]  
> The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
    "id": "id-value",
    "number": "10700",
    "displayName": "Inventory",
    "category": "Assets",
    "subCategory": "Inventory",
    "blocked": false,
    "lastModifiedDateTime": "2017-03-15T02:20:58.747Z"
}
```


## See also
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[Account](../resources/dynamics_account.md)  
[Get Aged Accounts Payable](dynamics_agedaccountspayable_get.md)  
[Get Aged Accounts Receivable](dynamics_agedaccountsreceivable_get.md)  
