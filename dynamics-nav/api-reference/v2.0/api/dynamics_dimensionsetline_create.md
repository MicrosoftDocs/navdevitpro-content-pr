---
title: CREATE dimensionSetLines | Microsoft Docs
description: Creates a dimensionSetLine object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/15/2020
ms.author: solsen
---

# Create dimensionSetLines
Create a dimensionSetLine object in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request
Replace the URL prefix for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] depending on environment following the [guideline](../../v2.0/endpoints-apis-for-dynamics.md).
```
POST businesscentralPrefix/companies({id})/dimensionSetLines
```

## Request headers

|Header         |Value                    |
|---------------|-------------------------|
|Authorization  |Bearer {token}. Required.|
|Content-Type   |application/json         |

## Request body
In the request body, supply a JSON representation of **dimensionSetLines** object.

## Response
If successful, this method returns ```201 Created``` response code and a **dimensionSetLines** object in the response body.

## Example

**Request**

Here is an example of a request.

```json
POST https://{businesscentralPrefix}/api/v2.0/companies({id})/dimensionSetLines
Content-type: application/json

{
    "id": "55c99ea7-bde4-ea11-bbf2-00155df3a615",
    "code": "BUSINESSGROUP",
    "parentId": "85d8a1c5-bde4-ea11-bbf2-00155df3a615",
    "parentType": "Sales Order",
    "displayName": "Business Group",
    "valueId": "56c99ea7-bde4-ea11-bbf2-00155df3a615",
    "valueCode": "HOME",
    "valueDisplayName": "Home"
}
```

**Response**

Here is an example of the response. 


## See also
[Tips for working with the APIs](/dynamics365/business-central/dev-itpro/developer/devenv-connect-apps-tips)     
[dimensionSetLine](../resources/dynamics_dimensionSetLine.md)  
<!--links-->

