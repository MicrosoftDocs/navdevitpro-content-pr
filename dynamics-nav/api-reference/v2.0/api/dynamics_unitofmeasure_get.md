---
title: GET unitOfMeasures | Microsoft Docs
description: Gets a unitOfMeasure object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/17/2020
ms.author: solsen
---

# Get unitOfMeasures
Retrieve the properties and relationships of a unitOfMeasure object for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)]. 


## HTTP request
Replace the URL prefix for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] depending on environment following the [guideline](../../v2.0/endpoints-apis-for-dynamics.md).
```
GET businesscentralPrefix/companies({id})/unitOfMeasures({id})
```

## Request headers

|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and an **unitOfMeasures** object in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://{businesscentralPrefix}/api/v2.0/companies({id})/unitOfMeasures({id})
```

**Response**

Here is an example of the response. 

```json
{
}
```


## See also
[Tips for working with the APIs](/dynamics365/business-central/dev-itpro/developer/devenv-connect-apps-tips)  
[unitOfMeasure](../resources/dynamics_unitOfMeasure.md)  
<!--links-->
