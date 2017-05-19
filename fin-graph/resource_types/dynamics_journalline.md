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

# Journal line resource type
Represents a journalLine resource type in Dynamics 365 for Financials.

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET journalLine](../api/dynamics_get_journalline.md)|journalLines|Get Journal Line.|
|[POST journalLine](../api/dynamics_create_journalline.md)|journalLines|Create Journal Line.|
|[PATCH journalLine](../api/dynamics_update_journalline.md)|journalLines|Update Journal Line.|
|[DELETE journalLine](../api/dynamics_delete_journalline.md)|none|Delete Journal Line.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the journal line. Read-Only.|
|lineNumber|integer|The number of the journal line.|
|accountId|GUID|The unique ID of the account that the journal line is related to.|
|accountNumber|string, maximum size 20|The number of the account that the journal line is related to.|
|postingDate|date|The date that the journal line is posted.|
|documentNumber|string, maximum size 20|Specifies a document number for the journal line.|
|externalDocumentNumber|string, maximum size 20|Specifies an external document number for the journal line.|
|amount|decimal|Specifies the total amount (including VAT) that the journal line consists of.|
|description|string, maximum size 50|The description of the journal line, provided by the user or autocreated.|
|comment|string, maximum size 250|A user specified comment on the journal line.|
|financialDimension1|string, maximum size 20|Specifies the dimension 1 value code that the journal line is linked to.|
|financialDimension2|string, maximum size 20|Specifies the dimension 2 value code that the journal line is linked to.|
|lastModifiedDateTime|datetime|The last datetime the journal line was modified. Read-Only.|


## Relationships
None

## JSON representation

Here is a JSON representation of the resource.


```json
{
    "id": "GUID",
    "lineNumber": integer,
    "accountId": "GUID",
    "accountNumber": "string",
    "postingDate": "date",
    "documentNumber": "string",
    "externalDocumentNumber": "string",
    "amount": decimal,
    "description": "string",
    "comment": "string",
    "financialDimension1": "string",
    "financialDimension2": "string",
    "lastModifiedDateTime": "datetime"
}
```

## See also
[Working with Dynamics 365 for Finance and Operations, Business Edition in Microsoft Graph](../resource_types/dynamics_overview.md) 
