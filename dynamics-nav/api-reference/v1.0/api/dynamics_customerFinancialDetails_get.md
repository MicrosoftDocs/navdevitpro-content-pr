---
title: Get customerFinancialDetails | Microsoft Docs
description: Gets customerFinancialDetails in Dynamics 365 Business Central.
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

# Get itemCategories
Retrieve the properties and relationships of a customerFinancialDetails object for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP requests

```
GET /businesscentral/companies({id})/customerFinancialDetails
GET /businesscentral/companies({id})/customers?$expand=customerFinancialDetails
GET /businesscentral/companies({id})/customers({customerId})?$expand=customerFinancialDetails
```

## Request headers

|Header       |Value                    |
|-------------|-------------------------|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and an **customerFinancialDetails** object in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://api.businesscentral.dynamics.com/v1.0/api/v1.0/companies({id})/customerFinancialDetails
```

**Response**

Here is an example of the response. 

> [!NOTE]  
>   The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
    {
        "id": "50168e70-ec57-45cf-86d4-3d850e361606",
        "number": "50000",
        "balance": 8836.8,
        "totalSalesExcludingTax": 81049,
        "overdueAmount": 5754.96
    }  
```


## See also

[Error Codes](../dynamics_error_codes.md)  
[customerFinancialDetails resource](../resources/dynamics_customerFinancialDetails.md)  