---
title: journal line resource type | Microsoft Docs
description: A journal line.
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

# Journal Line resource type
Represents a journalLine resource type in [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET journalLine](get-journalLine.md)|journalLines|Get Journal Line.|
|[POST journalLine](create-journalLine.md)|journalLines|Create Journal Line.|
|[PATCH journalLine](update-journalLine.md)|journalLines|Update Journal Line.|
|[DELETE journalLine](delete-journalLine.md)|none|Delete Journal Line.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the journal line. Read-Only.|
|accountId|GUID|The unique ID of the account that the journal line is related to.|
|accountNumber|string|The number of the account that the journal line is related to.|
|amount|decimal|Specifies the total amount (including VAT) that the journal line consists of.|
|lineNumber|string|The number of the journal line.|
|documentNumber|string|Specifies a document number for the journal line.|
|externalDocumentNumber|string|Specifies an external document number for the journal line.|
|description|string|The description of the journal line, provided by the user or autocreated.|
|comment|string|A user specified comment on the journal line.|
|postingDate|date|The date that the journal line is posted. Read-Only.|
|lastModifiedDateTime|datetime|The last datetime the journal line was modified. Read-Only.|


## Relationships
None

## JSON representation

Here is a JSON representation of the resource.


```json
{
"id": "GUID",
"accountId": "GUID",
"accountNumber": "string",
"amount": "decimal",
"lineNumber": "string",
"documentNumber": "string",
"externalDocumentNumber": "string",
"description": "string",
"comment": "string",
"postingDate": "date",
"lastModifiedDateTime": "datetime"
}
```

## See Also
[Graph Reference](graph-reference.md)  
