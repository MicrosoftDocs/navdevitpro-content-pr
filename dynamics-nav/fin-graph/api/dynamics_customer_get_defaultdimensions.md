---
title: Get defaultDimensions Customer | Microsoft Docs
description: Gets a customer default dimensions in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/20/2018
ms.author: solsen
---

# Get defaultDimensions Customer
Gets the default dimensions of the customer entity. 

## HTTP request 
The following example gets the default dimensions of the customer entity in the response body.

```
GET /businesscentral/companies({companyId})/customers({customerId})/defaultDimensions
```
## Request header
|Header|Value|
|------|-----|
|Authorization|	Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response 

If successful, this method returns a `200 OK` response code and the **default dimensions** in the response body.

## Example 

**Request**
Here is an example of a request. 

```json
GET https://api.businesscentral.dynamics.com/v1.0/api/beta/companies({companyId})/customers({customerId})/defaultDimensions
```

**Response**  
Here is an example of the response.

> [!NOTE]  
> The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
    "@odata.context":"http://api.businesscentral.dynamics.com/v1.0/api/beta/$metadata#companies(5106c77d-af37-4e2d-bb88-45d87aba1033)/customers(b3fbe87a-61b8-4a6c-85de-0555f1627a67)/defaultDimensions",
    "value":
    [
        {
            "@odata.etag":"W/\"JzQ0OzNPaHFuS0ZQdk5oc3ZkSW9KdzVkdXk2LytjcmNqeHJJOU05SjZ1aFBYVjQ9MTswMDsn\"",
            "parentId":"b3fbe87a-61b8-4a6c-85de-0555f1627a67","dimensionId":"d5fc81ea-8687-4e9d-9c49-7fde28ccdb1a",
            "dimensionCode":"DEPARTMENT",
            "dimensionValueId":"1045a902-070a-4d31-b2b1-b9431e9e5b26",
            "dimensionValueCode":"PROD",
            "valuePosting":"Same Code"
        }
    ]
} 
```

## See Also
[Customers](../resources/dynamics_customer.md)  
[Get Customers](dynamics_customer_get.md)  
[Post Customers](dynamics_create_customer.md)  
[Update Customer](dynamics_customer_update.md)  
[Delete Customer](dynamics_customer_delete.md)  
[Create defaultDimensions Customer](dynamics_customer_create_defaultdimensions.md)  
[Update defaultDimensions Customer](dynamics_customer_update_defaultdimensions.md)  
[Delete defaultDimensions Customer](dynamics_customer_delete_defaultdimensions.md)  

