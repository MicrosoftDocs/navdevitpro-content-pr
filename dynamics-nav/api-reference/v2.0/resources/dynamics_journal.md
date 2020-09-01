---
title: journal resource type | Microsoft Docs
description: A journal in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# journal resource type
Represents a journal in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method                                            |Return Type|Description    |
|:--------------------------------------------------|:----------|:--------------|
|[GET journal](../api/dynamics_journal_get.md)      |journal    |Gets a journal.   |
|[POST journal](../api/dynamics_create_journal.md)  |journal    |Creates a journal.|
|[PATCH journal](../api/dynamics_journal_update.md) |journal    |Updates a journal.|
|[DELETE journal](../api/dynamics_journal_delete.md)|none       |Deletes a journal.|


## Navigation

| Navigation |Return Type| Description |
|:----------|:----------|:-----------------|
|[account](../resources/dynamics_account.md)|account   |Gets the account of the journal.|
|[journalLines](../resources/dynamics_journallines.md)|journalLines   |Gets the journallines of the journal.|



## Properties

| Property           | Type                  |Description                                           |
|:-------------------|:----------------------|:-----------------------------------------------------|
|id                  |GUID                   |The unique ID of the journal. Non-editable.           |
|code                |string, maximum size 10| The code of the journal.                             |
|displayName         |string, maximum size 50| The display name of the journal.                     |
|lastModifiedDateTime|datetime               |The last datetime the journal was modified. Read-Only.|

## Bound actions
The journal resource type offers a bound action called `post` which posts the corresponding general journal batch.

Posting the general journal batch is illustrated in the following example:  
`POST https://<server address>:<server API port>/<server instance name>/api/v2.0/companies({id})/journals({id})/Microsoft.NAV.post`.

The response has no content; the response code is 204.

## JSON representation

Here is a JSON representation of the resource.


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

[Get Journal](../api/dynamics_journal_get.md)  
[Create Journal](../api/dynamics_create_journal.md)  
[Update Journal](../api/dynamics_journal_update.md)  
[Delete Journal](../api/dynamics_journal_delete.md)  
