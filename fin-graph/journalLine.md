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

# journal line resource type

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|GET journal line|journal line|Get journal line object.|
|CREATE journal line|journal line|Create journal line object.|
|UPDATE journal line|journal line|Update journal line object.|
|DELETE journal line|none|Delete journal line object.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the journal line. Read only.|
|accountId|GUID|The unique ID of the account that the journal line is related to.|
|accountNumber|string|The number of the account that the journal line is related to.|
|amount|decimal|Specifies the total amount (including VAT) that the journal line consists of.|
|lineNumber|string|The number of the journal line.|
|documentNumber|string|Specifies a document number for the journal line.|
|externalDocumentNumber|string|Specifies an external document number for the journal line.|
|description|string|The description of the journal line, provided by the user or autocreated.|
|comment|string|A user specified comment on the journal line.|
|postingDate|date|The date that the journal line is posted.|
|lastModifiedDateTime|datetime|The last datetime the journal line was modified. Read only.|


## Relationships
None

## JSON representation

Here is a JSON representation of the resource.


```json
{
"id": "45f5574a-271b-4789-87dd-4af2eeb7f362",
"accountId": "1ec4003c-93a5-4bfe-92ef-7be0c9121d69",
"accountNumber": "5710",
"amount": 15.81,
"lineNumber": 510000,
"documentNumber": "G00002",
"externalDocumentNumber": "",
"description": "Invoice no. 156786 for Gasoline 2019",
"comment": "",
"postingDate": "2019-01-25",
"lastModifiedDateTime": "0001-01-01T00:00:00Z",
}

```

## See Also
[Graph Reference](graph-reference.md)  
