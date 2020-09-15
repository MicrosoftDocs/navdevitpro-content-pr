---
title: CREATE bankAccounts | Microsoft Docs
description: Creates a bankAccount object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/15/2020
ms.author: solsen
---

# Create bankAccounts
Create a bankAccount object in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request
Replace the URL prefix for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] depending on environment following the [guideline](../../v2.0/endpoints-apis-for-dynamics.md).
```
POST businesscentralPrefix/companies({id})/bankAccounts
```

## Request headers

|Header         |Value                    |
|---------------|-------------------------|
|Authorization  |Bearer {token}. Required.|
|Content-Type   |application/json         |

## Request body
In the request body, supply a JSON representation of **bankAccounts** object.

## Response
If successful, this method returns ```201 Created``` response code and a **bankAccounts** object in the response body.

## Example

**Request**

Here is an example of a request.

```json
POST https://{businesscentralPrefix}/api/v2.0/companies({id})/bankAccounts
Content-type: application/json

{
}
```

**Response**

Here is an example of the response. 


## See also
[Tips for working with the APIs](/dynamics365/business-central/dev-itpro/developer/devenv-connect-apps-tips)     
[bankAccount](../resources/dynamics_bankAccount.md)  
<!--links-->
