---
title: Update paymentTerms | Microsoft Docs
description: Updates a payment term object in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/01/2019
ms.author: solsen
---

# Update paymentTerms
Update the properties of a payment terms object for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request
Replace the URL prefix for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] depending on environment following the [guideline](../../v1.0/endpoints-apis-for-dynamics.md).
```
PATCH businesscentralPrefix/companies({id})/paymentTerms({id})
```

## Request headers

|Header        |Value                    |
|--------------|-------------------------|
|Authorization |Bearer {token}. Required.|
|Content-Type  |application/json         |
|If-Match      |Required. When this request header is included and the eTag provided does not match the current tag on the **paymentTerms**, the **paymentTerms** will not be updated. |

## Request body
In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

## Response
If successful, this method returns a ```200 OK``` response code and an updated **paymentTerms** object in the response body.

## Example

**Request**

Here is an example of the request.
```json
PATCH https://{businesscentralPrefix}/api/v1.0/companies({id})/paymentTerms({id})
Content-type: application/json

{
  "displayName": "Net 7 days with Discount",
  "discountPercent": 10
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
  "code": "7 DAYS",
  "displayName": "Net 7 days with Discount",
  "dueDateCalculation": "7D",
  "discountDateCalculation": "",
  "discountPercent": 10,
  "calculateDiscountOnCreditMemos": false,
  "lastModifiedDateTime": "2017-03-15T02:20:55.203Z"
}
```


## See also

[Payment Terms](../resources/dynamics_paymentterms.md)  
[Get Payment Terms](../api/dynamics_paymentterms_get.md)  
[Create Payment Terms](../api/dynamics_create_paymentterms.md)  
[Delete Payment Terms](../api/dynamics_paymentterms_delete.md)  