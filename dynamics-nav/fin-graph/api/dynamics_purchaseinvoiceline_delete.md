---
title: Delete purchaseInvoiceLines | Microsoft Docs
description: Deletes a purchase invoice line object in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/05/2018
ms.author: solsen
ROBOTS: NOINDEX
---

# Delete purchaseInvoiceLines
Delete a purchase invoice line object from [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request
Replace the URL prefix for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] depending on environment following the [guideline](../../api-reference/v1.0/endpoints-apis-for-dynamics.md).
```
DELETE businesscentralPrefix/companies({id})/purchaseInvoices({id})/purchaseInvoiceLines(documentId=({id}),sequence=({number}))
```

## Request headers

|Header         |Value                      |
|---------------|---------------------------|
|Authorization  |Bearer {token}. Required.  |
|If-Match       |Required. When this request header is included and the eTag provided does not match the current tag on the **purchaseInvoiceLines**, the **purchaseInvoiceLines** will not be deleted.  |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns ```204 No Content``` response code. It does not return anything in the response body.

## Example

**Request**

Here is an example of the request.

```json
DELETE https://{businesscentralPrefix}/api/beta/companies({id})/purchaseInvoices({id})/purchaseInvoiceLines(documentId=({id}),sequence=({number}))
```

**Response** 

Here is an example of the response. 

```json
HTTP/1.1 204 No Content
```

## See also
[Tips for working with the APIs](business-central/dev-itpro/developer/devenv-connect-apps-tips)
[Graph Reference](../api/dynamics_graph_reference.md)  
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[Purchase Invoice Line](../resources/dynamics_purchaseinvoiceline.md)  
[Get Purchase Invoice Line](../api/dynamics_purchaseinvoiceline_get.md)  
[Create Purchase Invoice Line](../api/dynamics_create_purchaseinvoiceline.md)  
[Update Purchase Invoice Line](../api/dynamics_purchaseinvoiceline_update.md)  