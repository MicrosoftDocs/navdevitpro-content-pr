---
title: timeRegistrationEntry resource type | Microsoft Docs
description: An timeRegistrationEntry object in Dynamics 365 Business Central.
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

# timeRegistrationEntry resource type
Represents an timeRegistrationEntry in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Microsoft Dynamics NAV](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method                                              | Return Type|Description               |
|:----------------------------------------------------|:-----------|:-------------------------|
|[GET timeRegistrationEntries](../api/dynamics_timeregistrationentry_get.md)      |employees  |Get an timeRegistrationEntries object.   |
|[POST timeRegistrationEntries](../api/dynamics_timeregistrationentry_create.md)  |employees  |Create an timeRegistrationEntries object.|
|[PATCH timeRegistrationEntries](../api/dynamics_timeregistrationentry_update.md) |employees  |Update an timeRegistrationEntries object.|
|[DELETE timeRegistrationEntries](../api/dynamics_timeregistrationentry_delete.md)|none       |Delete an timeRegistrationEntries object.|



## Properties

| Property           | Type   |Description                                            |
|:-------------------|:-------|:------------------------------------------------------|
|id                  |GUID    |Id of the employee timeregistration Non-editable.      |
|employeeId              |GUID  |The employee Id. Read-Only.                        |
|employeeNumber         |string, maximum length 20  |The employee number.           |
|lineNumber           |integer  |line number of time registration.                        |
|date          |Date  |date of the time registration.                       |
|quantity             |decimal  |Quantity registered                            |
|status             |string  |The surname of the employee                            |
|unitOfMeasureId|GUID|The Id of the unit of measure for the registration.|
|unitOfMeasure|[NAV.UnitOfMeasure](../resources/dynamics_complextypes.md)|The unit of measure complex type.|
|lastModifiedDateTime|datetime|The last datetime the entity was modified.|

## Relationships
None

## JSON representation

Here is a JSON representation of the resource.


```json
{
    "id": "GUID",
    "employeeId": "GUID",
    "employeeNumber": "string",
    "linenumber": "integer",
    "date": "date",
    "quantity": "decimal",
    "status": "string",
    "unitOfMeasureId": "GUID",
    "unitOfMeasure": "NAV.UnitOfMeasure",
    "lastModifiedDateTime": "datetime"
}
```
## See also

[Error Codes](../dynamics_error_codes.md)  
[timeRegistrationEntries](../resources/dynamics_timeregistrationentry.md)  
[Get timeRegistrationEntries](../api/dynamics_timeregistrationentry_get.md)  
[Post timeRegistrationEntries](../api/dynamics_timeregistrationentry_create.md)  
[Patch timeRegistrationEntries](../api/dynamics_timeregistrationentry_update.md)  
[Delete timeRegistrationEntries](../api/dynamics_timeregistrationentry_delete.md)  
