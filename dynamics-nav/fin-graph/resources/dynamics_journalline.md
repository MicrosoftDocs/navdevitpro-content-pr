---
title: journalLines resource type | Microsoft Docs
description: A journal line in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/11/2017
ms.author: solsen
---

# journalLines resource type
Represents a line in a journal in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md).

## Methods

| Method                                                    | Return Type|Description         |
|:----------------------------------------------------------|:-----------|:-------------------|
|[GET journalLines](../api/dynamics_journalline_get.md)      |journalLines|Gets a journal line.   |
|[POST journalLines](../api/dynamics_create_journalline.md)  |journalLines|Creates a journal line.|
|[PATCH journalLines](../api/dynamics_journalline_update.md) |journalLines|Updates a journal line.|
|[DELETE journalLines](../api/dynamics_journalline_delete.md)|none        |Deletes a journal line.|

## Properties
| Property	           | Type	                |Description                                                        |
|:---------------------|:-----------------------|:------------------------------------------------------------------|
|id                    |GUID                    |The unique ID of the journal line. Non-editable.                   |
|journalDisplayName    |string, maximum size 10 |The display name of the journal that this line belongs to. Read-Only.|
|lineNumber            |integer                 |The number of the journal line.                                    |
|accountId             |GUID                    |The unique ID of the account that the journal line is related to.  |
|accountNumber         |string, maximum size 20 |The number of the account that the journal line is related to.     |
|postingDate           |date                    |The date that the journal line is posted.                          |
|documentNumber        |string, maximum size 20 |Specifies a document number for the journal line.                  |
|externalDocumentNumber|string, maximum size 20 |Specifies an external document number for the journal line.        |
|amount                |decimal                 |Specifies the total amount (including VAT) that the journal line consists of.|
|description           |string, maximum size 50 |The description of the journal line, provided by the user or autocreated.|
|comment               |string, maximum size 250|A user specified comment on the journal line.                      |
|lastModifiedDateTime  |datetime                |The last datetime the journal line was modified. Read-Only.        |

## Relationships
A journal line is a subpage of a journal. It cannot be accessed directly.

A journal line can be a "Parent Entity" of the dimension lines.

An Account (accountId) must exist in the Accounts table.


## JSON representation

Here is a JSON representation of the resource.


```json
{
    "id": "GUID",
    "journalDisplayName": "string",
    "lineNumber": "integer",
    "accountId": "GUID",
    "accountNumber": "string",
    "postingDate": "date",
    "documentNumber": "string",
    "externalDocumentNumber": "string",
    "amount": "decimal",
    "description": "string",
    "comment": "string",
    "lastModifiedDateTime": "datetime"
}
```

## See also
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md) 
