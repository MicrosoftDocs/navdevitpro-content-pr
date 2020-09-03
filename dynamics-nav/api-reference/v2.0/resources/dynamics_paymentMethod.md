---
title: paymentMethod resource type | Microsoft Docs
description: An payment method object in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# paymentMethod resource type
Represents an payment method in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method                                              | Return Type|Description               |
|:----------------------------------------------------|:-----------|:-------------------------|
|[GET paymentMethod](../api/dynamics_paymentMethod_get.md)      |employees  |Get an paymentMethod object.   |
|[POST paymentMethod](../api/dynamics_paymentMethod_create.md)  |employees  |Create an paymentMethod object.|
|[PATCH paymentMethod](../api/dynamics_paymentMethod_update.md) |employees  |Update an paymentMethod object.|
|[DELETE paymentMethod](../api/dynamics_paymentMethod_delete.md)|none       |Delete an paymentMethod object.|




## Navigation

| Navigation |Return Type| Description |
|:----------|:----------|:-----------------|
|[account](../resources/dynamics_account.md)|account   |Gets the account of the paymentMethod.|
|[attachments](../resources/dynamics_attachments.md)|attachments   |Gets the attachments of the paymentMethod.|
|[dimensionSetLines](../resources/dynamics_dimensionsetlines.md)|dimensionSetLines   |Gets the dimensionsetlines of the paymentMethod.|

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

## JSON representation

Here is a JSON representation of the resource.


```json
{
   "id": "GUID",
   "code": "string",
   "displayName": "string",
   "lastModifiedDateTime": "datetime"
}
```
## See also

[Error Codes](../dynamics_error_codes.md)  
[paymentMethod](../resources/dynamics_paymentMethod.md)  
[Get paymentMethod](../api/dynamics_paymentMethod_get.md)  
[Post paymentMethod](../api/dynamics_paymentMethod_create.md)  
[Patch paymentMethod](../api/dynamics_paymentMethod_update.md)  
[Delete paymentMethod](../api/dynamics_paymentMethod_delete.md)  
