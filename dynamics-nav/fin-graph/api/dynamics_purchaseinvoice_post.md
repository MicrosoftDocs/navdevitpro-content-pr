---
title: Post purchase invoices | Microsoft Docs
description: Posts a purchase invoice in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/28/2018
ms.author: solsen
---

# Posts purchase invoices
Posts a purchase invoice for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request
```
POST /businesscentral/companies({id})/purchaseinvoices({invoiceid})/Microsoft.NAV.post
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```204``` response code.

## Example

**Request**

Here is an example of the request.
```json
POST https://api.businesscentral.dynamics.com/v1.0/api/beta/companies({companyId})/purchaseinvoices({invoiceId})/Microsoft.NAV.post
```
**Response**

Here is an example of the response. 
```json
HTTP/1.1 204 No Content
```

## See also
[Graph Reference](../api/dynamics_graph_reference.md)  
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[Purchase Invoice](../resources/dynamics_purchaseinvoice.md)  
[Create Purchase Invoice](../api/dynamics_purchaseinvoice_get.md)  
[Update Purchase Invoice](../api/dynamics_purchaseinvoice_update.md)  
[Delete Purchase Invoice](../api/dynamics_purchaseinvoice_delete.md)  