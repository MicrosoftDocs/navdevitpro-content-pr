---
title: Update vendors | Microsoft Docs
description: Updates a vendor object in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.prod: dynamics-nav-2018
ms.topic: reference
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/19/2018
ms.author: solsen
ROBOTS: NOINDEX
---

# Update vendors
Update the properties of a vendor object for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request
Replace the URL prefix for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] depending on environment following the [guideline](../../endpoints-apis-for-dynamics.md).
```
PATCH businesscentralPrefix/companies({id})/vendors({id})
```

## Request headers

|Header|Value|
|------|-----|
|Authorization |Bearer {token}. Required.|
|Content-Type  |application/json|
|If-Match      |Required. When this request header is included and the eTag provided does not match the current tag on the **vendors**, the **vendors** will not be updated. |

## Request body
In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

## Response
If successful, this method returns a ```200 OK``` response code and an updated **vendors** object in the response body.

## Example

**Request**

Here is an example of the request.
```json
PATCH https://{businesscentralPrefix}/api/beta/companies({id})/vendors({id})
Content-type: application/json

{
  "displayName": "Wide World Importers Inc.",
  "blocked": "Payment"
}
```

**Response**

Here is an example of the response. 

> [!NOTE]  
>   The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
HTTP/1.1 200 OK
Content-type: application/json

{
  "id": "id-value",
  "number": "40000",
  "displayName": "Wide World Importers Inc.",
  "address": {
    "street": "51 Radcroft Road",
    "city": "Atlanta",
    "state": "GA",
    "countryLetterCode": "US",
    "postalCode": "31772"
  },
  "phoneNumber": "",
  "email": "toby.rhode@cronuscorp.net",
  "website": "",
  "taxRegistrationNumber": "",
  "currencyCode": "USD",
  "irs1099Code": "",
  "paymentTermsId": "3bb5b4b6-ea4c-43ca-ba1c-3b69e29a6668",
  "paymentMethod": {
    "code": "BANK",
    "description": "Bank Transfer"
  },
  "taxLiable": true,
  "blocked": "Payment",
  "balance": 0,
  "lastModifiedDateTime": "2017-03-07T00:35:29.667Z"
}
```


## See also
[Tips for working with the APIs](/dynamics365/business-central/dev-itpro/developer/devenv-connect-apps-tips)  
[Graph Reference](../api/dynamics_graph_reference.md)  
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Dynamics 365 Business Central](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[Vendor](../resources/dynamics_vendor.md)  
[Get Vendor](../api/dynamics_vendor_get.md)  
[Create Vendor](../api/dynamics_create_vendor.md)  
[Delete Vendor](../api/dynamics_vendor_delete.md)  
