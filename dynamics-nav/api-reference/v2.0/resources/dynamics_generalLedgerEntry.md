---
title: generalLedgerEntry resource type | Microsoft Docs
description: An general ledger entry object in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# generalLedgerEntry resource type
Represents an general ledger entry in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method                                              | Return Type|Description               |
|:----------------------------------------------------|:-----------|:-------------------------|
|[GET General Ledger Entry](../api/dynamics_generalLedgerEntry_get.md)      |employees  |Get an General Ledger Entry object.   |
|[POST General Ledger Entry](../api/dynamics_generalLedgerEntry_create.md)  |employees  |Create an General Ledger Entry object.|
|[PATCH General Ledger Entry](../api/dynamics_generalLedgerEntry_update.md) |employees  |Update an General Ledger Entry object.|
|[DELETE General Ledger Entry](../api/dynamics_generalLedgerEntry_delete.md)|none       |Delete an General Ledger Entry object.|




## Navigation

| Navigation |Return Type| Description |
|:----------|:----------|:-----------------|
|[account](../resources/dynamics_account.md)|account   |Gets the account of the generalLedgerEntry.|
|[attachments](../resources/dynamics_attachments.md)|attachments   |Gets the attachments of the generalLedgerEntry.|
|[dimensionSetLines](../resources/dynamics_dimensionsetlines.md)|dimensionSetLines   |Gets the dimensionsetlines of the generalLedgerEntry.|

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
   "entryNumber": "integer",
   "postingDate": "date",
   "documentNumber": "string",
   "documentType": "string",
   "accountId": "GUID",
   "accountNumber": "string",
   "description": "string",
   "debitAmount": "decimal",
   "creditAmount": "decimal",
   "lastModifiedDateTime": "datetime"
}
```
## See also

[Error Codes](../dynamics_error_codes.md)  
[General Ledger Entry](../resources/dynamics_generalLedgerEntry.md)  
[Get General Ledger Entry](../api/dynamics_generalLedgerEntry_get.md)  
[Post General Ledger Entry](../api/dynamics_generalLedgerEntry_create.md)  
[Patch General Ledger Entry](../api/dynamics_generalLedgerEntry_update.md)  
[Delete General Ledger Entry](../api/dynamics_generalLedgerEntry_delete.md)  
