---
title: journal resource type | Microsoft Docs
description: A journal object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/15/2020
ms.author: solsen
---

# journal resource type
Represents an journal in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method              | Return Type|Description               |
|:--------------------|:-----------|:-------------------------|
|[GET journal](../api/dynamics_journal_Get.md)|journal|Gets a journal object.|
|[DELETE journal](../api/dynamics_journal_Delete.md)|journal|Deletes a journal object.|
|[POST journal](../api/dynamics_journal_Create.md)|journal|Creates a journal object.|
|[PATCH journal](../api/dynamics_journal_Update.md)|journal|Updates a journal object.|


## Bound Actions
post

## Navigation

| Navigation |Return Type| Description |    
|:----------|:----------|:-----------------|
|[account](../resources/dynamics_account.md)|account |Gets the account of the journal.|
|[journalLines](../resources/dynamics_journallines.md)|journalLines |Gets the journallines of the journal.|


## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|id|GUID|The unique ID of the item. Non-editable.|
|code|string|The code of the journal.|
|displayName|string|Specifies the journal's name. This name will appear on all sales documents for the journal.|
|lastModifiedDateTime|datetime|The last datetime the journal was modified. Read-Only.|
|balancingAccountId|GUID|The balancing G/L Account ID.|
|balancingAccountNumber|string|The balancing G/L Account number.|


## JSON representation

Here is a JSON representation of the journal resource.


```json
{
   "id": "GUID",
   "code": "string",
   "displayName": "string",
   "lastModifiedDateTime": "datetime",
   "balancingAccountId": "GUID",
   "balancingAccountNumber": "string"
}
```
## See also

[GET journal](../api/dynamics_journal_Get.md)
[DELETE journal](../api/dynamics_journal_Delete.md)
[POST journal](../api/dynamics_journal_Create.md)
[PATCH journal](../api/dynamics_journal_Update.md)

