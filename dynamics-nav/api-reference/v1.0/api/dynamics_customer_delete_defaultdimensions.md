---
title: Delete customer defaultDimensions | Microsoft Docs
description: Deletes the default dimensions of the customer in Dynamics 365 Business Central.
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

# Delete customer defaultDimensions
Deletes the default dimensions of the customer in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request
```
DELETE /businesscentral/companies({companyId})/customers({customerId})/defaultDimensions({customerId},{dimensionId})
```

## Request headers

|Header         |Value                     |
|---------------|--------------------------|
|Authorization  |Bearer {token}. Required. |
|If-Match       |Required. When this request header is included and the eTag provided does not match the current tag on the **customers**, the **customers** will not be updated. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```204 No Content``` response code and it deletes the default dimensions for the customer and corresponding dimension.

## Example

**Request**

Here is an example of the request.

```json
DELETE https://api.businesscentral.dynamics.com/v1.0/api/v1.0/companies({companyId})/customers({customerId})/defaultDimensions({customerId},{dimensionId})
```

**Response** 

No Content.

## See also

[Customer](../resources/dynamics_customer.md)  
[Create customer defaultDimensions](dynamics_customer_create_defaultdimensions.md)  
[Update customer defaultDimensions](dynamics_customer_update_defaultdimensions.md)  
[Get customer defaultDimensions](dynamics_customer_get_defaultdimensions.md)  
