---
title: Delete item defaultDimensions | Microsoft Docs
description: Deletes the default dimensions of the item in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/01/2019
ms.author: solsen
---

# Delete item defaultDimensions
Deletes the default dimensions of the item in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request
Replace the URL prefix for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] depending on environment following the [guideline](../../v1.0/endpoints-apis-for-dynamics.md).
```
DELETE businesscentralPrefix/companies({companyId})/items({itemId})/defaultDimensions({itemId},{dimensionId})
```

## Request headers

|Header         |Value                     |
|---------------|--------------------------|
|Authorization  |Bearer {token}. Required. |
|If-Match       |Required. When this request header is included and the eTag provided does not match the current tag on the **items**, the **items** will not be updated. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```204 No Content``` response code and it deletes the default dimensions for the item and corresponding dimension.

## Example

**Request**

Here is an example of the request.

```json
DELETE https://{businesscentralPrefix}/api/v1.0/companies({companyId})/items({itemId})/defaultDimensions({itemId},{dimensionId})
```

**Response** 

No Content.

## See also
[Tips for working with the APIs](/dynamics365/business-central/dev-itpro/developer/devenv-connect-apps-tips)  

[Item](../resources/dynamics_item.md)  
[Create item defaultDimensions](dynamics_item_create_defaultdimensions.md)  
[Update item defaultDimensions](dynamics_item_update_defaultdimensions.md)  
[Get item defaultDimensions](dynamics_item_get_defaultdimensions.md)  
