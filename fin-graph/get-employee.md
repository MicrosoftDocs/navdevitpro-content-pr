---
title: GET employee method | Microsoft Docs
description: Gets a Employee.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/13/2017
ms.author: solsen
---

# GET Employee Method
Retrieve the properties and relationships of an employee object for [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].

## HTTP request
```
GET /financials/companies/{id}/employees/{id}
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and employee object in the response body.

**Request**

Here is an example of the request.

```json
GET https://graph.microsoft.com/beta/financials/companies/{id}/employees/{id}
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
  "id": "id-value",
  "number": "TS",
  "displayName": "Timothy Sneath",
  "givenName": "Timothy",
  "middleName": "",
  "surname": "Sneath",
  "jobTitle": "Production Assistant",
  "address": {
    "street": "66B James Road",
    "city": "London",
    "state": "",
    "countryLetterCode": "",
    "postalCode": "N12 5XY"
  },
  "phoneNumber": "0678-8712-5466",
  "mobilePhone": "1234-6545-8799",
  "email": "",
  "personalEmail": "ts@cronus-demosite.com",
  "employmentDate": "1996-03-01",
  "terminationDate": "0001-01-01",
  "birthDate": "1963-12-07",
  "picture@odata.mediaReadLink": "https://graph.microsoft.com/beta/financials/companies/{id}/employees/{id}/picture",
  "lastModifiedDateTime": "2017-03-16T14:57:19.497Z"  
}
```

## See Also
[Microsoft Graph Reference](graph-reference.md)  
