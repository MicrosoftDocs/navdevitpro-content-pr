---
title: generalLedgerEntries resource type | Microsoft Docs
description: A general ledger entry in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/16/2017
ms.author: solsen
---

# generalLedgerEntries resource type
Represents a generalLedgerEntry object in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../includes/navnow_md.md)] see [Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md).

## Methods

| Method       | Return Type  |Description|
|:-------------|:-------------|:----------|
|[GET generalLedgerEntries](../api/dynamics_generalledgerentries_get.md)|generalLedgerEntries|Get a G/L entry object.|

## Properties
| Property	         | Type	                 |Description                                  |
|:-------------------|:----------------------|:--------------------------------------------|
|id                  |GUID                   |The unique ID of the G/L Entry.              |
|number              |numeric                |Specifies the number of the G/L Entry.       |
|postingDate         |date                   |Specifies the posting date of the G/L Entry. |
|documentNumber      |string, maximum size 20|Specifies the document number of the G/L Entry.|
|documentType        |string                 |Specifies the document type of the G/L Entry.|
|accountId           |GUID                   |Specifies the accountId of the G/L Entry.    |
|accountNumber       |string, maximum size 20|Specifies the accountNumber of the G/L Entry.|
|description         |string, maximum size 50|Specifies the description of the G/L Entry.  |
|debitAmount         |numeric                |Specifies the debitAmount of the G/L Entry.  |
|creditAmount        |numeric                |Specifies the creditAmount of the G/L Entry. |
|lastModifiedDateTime|datetime               |The last datetime the G/L Entry was modified.|


## Relationships
None

## JSON representation

Here is a JSON representation of the resource.


```json
{
  "id": "GUID",
  "number": "int",
  "postingDate": "Date",
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
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md) 
