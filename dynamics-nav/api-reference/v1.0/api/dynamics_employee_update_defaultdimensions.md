---
title: Update employee defaultDimensions | Microsoft Docs
description: Updates a employee default dimensions in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/01/2019
ms.author: solsen
---

# Update employee defaultDimensions
Updates the default dimensions of the employee in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].


## HTTP request
Replace the URL prefix for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] depending on environment following the [guideline](../../v1.0/endpoints-apis-for-dynamics.md).
```
PATCH businesscentralPrefix/companies({companyId})/employees({employeeId})/defaultDimensions({employeeId},{dimensionId})
```

## Request headers

|Header        |Value                    |
|--------------|-------------------------|
|Authorization |Bearer {token}. Required.|
|Content-Type  |application/json         |

## Request body
In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

> [!NOTE]  
> You cannot modify parentId, dimensionId or dimensionCode fields, because these are key fields, and rename is not allowed in Default Dimension record.

## Response
If successful, this method returns a `200 OK` response code and an updated default dimensions for the **employee** in the response body. 

## Example

**Request**

Here is an example of the request.

```json
PATCH https://{businesscentralPrefix}/api/v1.0/companies({companyId})/employees({employeeId})/defaultDimensions({employeeId},{dimensionId})
```

**Request body**

```
{
  "dimensionValueId":"1045a902-070a-4d31-b2b1-b9431e9e5b26",
  "postingValidation":"Same Code"
}
```

**Response**

Here is an example of the response. 

> [!NOTE]  
>   The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
    "@odata.context":"https://api.businesscentral.dynamics.com/v1.0/api/v1.0/$metadata#companies(5106c77d-af37-4e2d-bb88-45d87aba1033)/employees(b3fbe87a-61b8-4a6c-85de-0555f1627a67)/defaultDimensions",
    "value":
    [
        {
            "@odata.etag":"W/\"JzQ0OzNPaHFuS0ZQdk5oc3ZkSW9KdzVkdXk2LytjcmNqeHJJOU05SjZ1aFBYVjQ9MTswMDsn\"",
            "parentId":"b3fbe87a-61b8-4a6c-85de-0555f1627a67",
            "dimensionId":"d5fc81ea-8687-4e9d-9c49-7fde28ccdb1a",
            "dimensionCode":"DEPARTMENT",
            "dimensionValueId":"1045a902-070a-4d31-b2b1-b9431e9e5b26",
            "dimensionValueCode":"PROD",
            "postingValidation":"Same Code"
        }
    ]
}
```

## See also
[Tips for working with the APIs](/dynamics365/business-central/dev-itpro/developer/devenv-connect-apps-tips)  

[Employees](../resources/dynamics_employee.md)  
[Create employee defaultDimensions](dynamics_employee_create_defaultdimensions.md)  
[Get employee defaultDimensions](dynamics_employee_get_defaultdimensions.md)  
[Delete employee defaultDimensions](dynamics_employee_delete_defaultdimensions.md)  