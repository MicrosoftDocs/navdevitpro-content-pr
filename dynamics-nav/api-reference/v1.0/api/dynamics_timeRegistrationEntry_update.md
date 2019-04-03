---
title: Patch timeRegistrationEntries| Microsoft Docs
description: Patch a timeRegistrationEntries in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
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

# Update timeRegistrationEntries
Update a timeRegistrationEntry in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].


## HTTP request
```
PATCH /businesscentral/companies({companyId})/timeRegistrationEntries({timeregistrationId})
```

## Request headers

|Header        |Value                    |
|--------------|-------------------------|
|Authorization |Bearer {token}. Required.|
|Content-Type  |application/json         |
|If-Match  |*application/json*         |


## Example

**Request**

Here is an example of the request.
```json
PATCH https://api.businesscentral.dynamics.com/v1.0/api/v1.0/companies({id})/timeRegistrationEntries({timeregistrationId})
Content-type: application/json

{
	"quantity": 8
}
```

**Response**

Here is an example of the response. 

> [!NOTE]  
>   The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
HTTP/1.1 200 OK
Content-type: application/json

{
    "id": "967b7868-5e15-4adc-9698-cd88e509395b",
    "employeeId": "dd6ce54a-d14f-40dc-a10d-1d4d18758c76",
    "employeeNumber": "RL",
    "lineNumber": 10000,
    "date": "2019-01-02",
    "quantity": 8,
    "status": "Open",
    "unitOfMeasureId": "a7ec16cb-014f-446a-a084-bc31d5d7e742",
    "lastModfiedDateTime": "2019-03-25T14:26:55.027Z",
    "unitOfMeasure": {
        "code": "HOUR",
        "displayName": "Hour",
        "symbol": null,
        "unitConversion": null
    }
}
```

## See also
[Error Codes](../dynamics_error_codes.md)  
[timeRegistrationEntries](../resources/dynamics_timeRegistrationEntry.md)  
[Get timeRegistrationEntries](../api/dynamics_timeRegistrationEntry_get.md)  
[Post timeRegistrationEntries](../api/dynamics_timeRegistrationEntry_create.md)  
[Patch timeRegistrationEntries](../api/dynamics_timeRegistrationEntry_update.md)  
[Delete timeRegistrationEntries](../api/dynamics_timeRegistrationEntry_delete.md)  
