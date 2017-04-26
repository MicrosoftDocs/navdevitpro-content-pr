---
title: CREATE employee method | Microsoft Docs
description: Creates an employee.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/16/2017
ms.author: solsen
---

# POST Employee Method
Create an employee in [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].

## HTTP request
```
POST /financials/companies/{id}/employees
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer. Required.  |
|Content-Type  |application/json  |

## Request body
In the request body, supply a JSON representation of employees object.

## Response
If successful, this method returns ```201 Created``` response code and employees object in the response body.

## Example

**Request**

Here is an example of a request.

```json
POST https://graph.microsoft.com/beta/finacials/companies/{id}/employees
Content-type: application/json

{
  "id": "id-value",
  "number": "TS",
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
}

```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
HTTP/1.1 201 Created
Content-type: application/json

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
