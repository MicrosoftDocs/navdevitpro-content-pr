---
title: journal resource type | Microsoft Docs
description: A journal.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/03/2017
ms.author: solsen
---

# Journal resource type
Represents a journal in Dynamics 365 for Financials.

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET journal](../api/dynamics_get_journal.md)|journal|Get Journal.|
|[POST journal](../api/dynamics_create_journal.md)|journal|Create Journal.|
|[PATCH journal](../api/dynamics_update_journal.md)|journal|Update Journal.|
|[DELETE journal](../api/dynamics_delete_journal.md)|none|Delete Journal.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the journal. Read-Only.|
|code|string, maximum size 10| The code of the journal.|
|displayName|string, maximum size 50| The display name of the journal.|
|lastModifiedDateTime|datetime|The last datetime the journal was modified. Read-Only.|

## Relationships

## JSON representation

Here is a JSON representation of the resource.


```json
{
  "id": "GUID",
  "code": "String",
  "displayName": "String",
  "lastModifiedDateTime": "datetime"
}
```

## See also
[Graph Reference](../api/dynamics_graph_reference.md)  
