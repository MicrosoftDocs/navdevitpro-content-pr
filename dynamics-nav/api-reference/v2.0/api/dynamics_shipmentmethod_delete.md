---
title: DELETE shipmentMethods | Microsoft Docs
description: Deletes shipmentMethod  in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/01/2020
ms.author: solsen
---

# Delete shipmentMethods
Deletes shipmentMethods in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request
Replace the URL prefix for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] depending on environment following the [guideline](../../v2.0/endpoints-apis-for-dynamics.md).
```
DELETE businesscentralPrefix/companies({id})/shipmentMethods({id})
```

## Request headers

|Header         |Value                     |
|---------------|--------------------------|
|Authorization  |Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```204 No Content``` response code and it deletes the shipmentMethod .

## Example

**Request**

Here is an example of the request.

```json
DELETE https://{businesscentralPrefix}/api/v2.0/companies({id})/shipmentMethods({id})
```

**Response** 

No Content.



## See also
[Tips for working with the APIs](/dynamics365/business-central/dev-itpro/developer/devenv-connect-apps-tips)
[shipmentmethod](../resources/dynamics_shipmentmethod.md)[Get shipmentmethod](../api/dynamics_shipmentmethod_Get.md)
[Create shipmentmethod](../api/dynamics_shipmentmethod_Create.md)
[Update shipmentmethod](../api/dynamics_shipmentmethod_Update.md)
