---
title: account resource type | Microsoft Docs
description: An account.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/02/2017
ms.author: solsen
---

# account resource type

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|GET account|account|Get account object.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the account.|
|number|string|The number of the account.|
|displayName|string|The display name of the account.|
|category|string|The name of the category that the account belongs to.|
|subCategory|string|The name of the subCategory that the account belongs to.|
|blocked|boolean|The state of the account.|
|lastModifiedDateTime|datetime|The last datetime the account was modified.|


## Relationships
None

## JSON representation

Here is a JSON representation of the resource.


```json
{
  "id": "d5f85f49-746c-4f76-8c85-01b691c7cdfc",
  "number": "2340",
  "displayName": "Other Receivables",
  "category": "Assets",
  "subCategory": "Accounts Receivable",
  "blocked": false,
  "lastModifiedDateTime": "0001-01-01T00:00:00Z"
}

```
## See Also
[Graph Reference](graph-reference.md)  
