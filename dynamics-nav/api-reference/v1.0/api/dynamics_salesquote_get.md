---
title: Get salesQuotes | Microsoft Docs
description: Gets a sales quote object in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/01/2019
ms.author: solsen
---

# Get salesQuotes
Retrieve the properties and relationships of a sales quote object for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request
Replace the URL prefix for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] depending on environment following the [guideline](../../v1.0/endpoints-apis-for-dynamics.md).

```
GET businesscentralPrefix/companies({id})/salesQuotes({id})
```

## Request headers

|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and a **salesQuotes** object in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://{businesscentralPrefix}/api/v1.0/companies({id})/salesQuotes({id})
```

**Response**

Here is an example of the response. 

> [!NOTE]  
>   The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
  "id": "id-value",
  "number": "1006",
  "externalDocumentNumber": "",
  "documentDate": "2019-01-24",
  "dueDate": "2019-01-24",
  "customerId": "customerId-value",
  "contactId": "",
  "customerNumber": "10000",
  "customerName": "Coho Winery",
  "billingPostalAddress": {
    "street": "",
    "city": "",
    "state": "",
    "countryLetterCode": "",
    "postalCode": ""
  },
  "currencyId": "currencyId-value",
  "currencyCode": "GBP",
  "paymentTermsId": "3bb5b4b6-ea4c-43ca-ba1c-3b69e29a6668",
  "shipmentMethodId": "shipmentMethodId-value",
  "shipmentMethod": "EXW",
  "salesperson": "",
  "discountAmount": 0,
  "totalAmountExcludingTax": 6825.6,
  "totalTaxAmount": 682.56,
  "totalAmountIncludingTax": 7508.16,
  "status": "Open",
  "sentDate": "0001-01-01T00:00:00Z",
  "validUntilDate": "2019-01-24",
  "acceptedDate": "2019-01-24",
  "lastModifiedDateTime": "2017-03-17T19:02:22.043Z"
}
```

## See also
[Tips for working with the APIs](/dynamics365/business-central/dev-itpro/developer/devenv-connect-apps-tips)  

[Sales Quote](../resources/dynamics_salesquote.md)  
[Create Sales Quote](../api/dynamics_create_salesquote.md)  
[Update Sales Quote](../api/dynamics_salesquote_update.md)  
[Delete Sales Quote](../api/dynamics_salesquote_delete.md)  