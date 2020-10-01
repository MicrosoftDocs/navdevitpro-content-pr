---
title: timeRegistrationEntry resource type | Microsoft Docs
description: A time registration entry object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: "dynamics365-business-central"
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/01/2020
ms.author: solsen
---

# timeRegistrationEntry resource type
Represents a time registration entry in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods
| Method | Return Type|Description |
|:--------------------|:-----------|:-------------------------|
|[GET timeRegistrationEntry](../api/dynamics_timeRegistrationEntry_Get.md)|timeRegistrationEntry|Gets a time registration entry object.|
|[DELETE timeRegistrationEntry](../api/dynamics_timeRegistrationEntry_Delete.md)|none|Deletes a time registration entry object.|
|[POST timeRegistrationEntry](../api/dynamics_timeRegistrationEntry_Create.md)|timeRegistrationEntry|Creates a time registration entry object.|
|[PATCH timeRegistrationEntry](../api/dynamics_timeRegistrationEntry_Update.md)|timeRegistrationEntry|Updates a time registration entry object.|




## Navigation

| Navigation |Return Type| Description |    
|:----------|:----------|:-----------------|
|[employee](dynamics_employee.md)|employee |Gets the employee of the timeRegistrationEntry.|
|[project](dynamics_project.md)|project |Gets the project of the timeRegistrationEntry.|
|[unitOfMeasure](dynamics_unitofmeasure.md)|unitOfMeasure |Gets the unitofmeasure of the timeRegistrationEntry.|
|[dimensionSetLines](dynamics_dimensionsetlines.md)|dimensionSetLines |Gets the dimensionsetlines of the timeRegistrationEntry.|


## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|id|GUID|The unique ID of the item. Non-editable.|
|employeeId|GUID|The unique ID of employee.|
|employeeNumber|string|The employee's number.|
|jobId|GUID|The ID of the time registration entry job.|
|jobNumber|string|The number of the time registration entry job.|
|jobTaskNumber|string|The number of the job task.|
|absence|string|The cause of absence code.|
|lineNumber|integer|The time registration entry item line number.|
|date|date|The date of the time registration entry.|
|quantity|decimal|The quantity of the item in the time registration entry.|
|status|NAV.employeeTimeRegStatus|Specifies the status of the time registration entry. It can be "Open", "Submitted", "Rejected" or "Approved".|
|unitOfMeasureId|GUID|The ID of unit of measure for the time registration entry.|
|unitOfMeasureCode|string|The code of unit of measure for the time registration entry.|
|lastModfiedDateTime|datetime|The last datetime the time registration entry was modified. Read-Only.|


## JSON representation

Here is a JSON representation of the timeRegistrationEntry resource.


```json
{
   "id": "GUID",
   "employeeId": "GUID",
   "employeeNumber": "string",
   "jobId": "GUID",
   "jobNumber": "string",
   "jobTaskNumber": "string",
   "absence": "string",
   "lineNumber": "integer",
   "date": "date",
   "quantity": "decimal",
   "status": "NAV.employeeTimeRegStatus",
   "unitOfMeasureId": "GUID",
   "unitOfMeasureCode": "string",
   "lastModfiedDateTime": "datetime"
}
```
## See also

[GET timeRegistrationEntry](../api/dynamics_timeRegistrationEntry_Get.md)   
[DELETE timeRegistrationEntry](../api/dynamics_timeRegistrationEntry_Delete.md)   
[POST timeRegistrationEntry](../api/dynamics_timeRegistrationEntry_Create.md)   
[PATCH timeRegistrationEntry](../api/dynamics_timeRegistrationEntry_Update.md)   

