---
title: GET customerPaymentJournals | Microsoft Docs
description: Gets a customerPaymentJournal object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/17/2020
ms.author: solsen
---

# Get customerPaymentJournals
Retrieve the properties and relationships of a customerPaymentJournal object for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)]. 


## HTTP request
Replace the URL prefix for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] depending on environment following the [guideline](../../v2.0/endpoints-apis-for-dynamics.md).
```
GET businesscentralPrefix/companies({id})/customerPaymentJournals({id})
```

## Request headers

|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and an **customerPaymentJournals** object in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://{businesscentralPrefix}/api/v2.0/companies({id})/customerPaymentJournals({id})
```

**Response**

Here is an example of the response. 

```json
{
}
```


## See also
[Tips for working with the APIs](/dynamics365/business-central/dev-itpro/developer/devenv-connect-apps-tips)  
[customerPaymentJournal](../resources/dynamics_customerPaymentJournal.md)  
<!--links-->
