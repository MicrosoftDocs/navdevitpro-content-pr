---
title: customerPaymentsJournals resource type | Microsoft Docs
description: A customer payments journal in Dynamics 365 for Financials.
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

# customerPaymentsJournals resource type
Represents a customer payments journal in Dynamics 365 for Financials.

## Methods

| Method                                                                              | Return Type             |Description                      |
|:------------------------------------------------------------------------------------|:------------------------|:--------------------------------|
|[GET customerPaymentsJournals](../api/dynamics_customerpaymentsjournal_get.md)      |customerPaymentsJournals|Gets a customer payments journal.   |
|[POST customerPaymentsJournals](../api/dynamics_create_customerpaymentsjournal.md)  |customerPaymentsJournals|Creates a customer payments journal.|
|[PATCH customerPaymentsJournals](../api/dynamics_customerpaymentsjournal_update.md) |customerPaymentsJournals|Updates a customer payments journal.|
|[DELETE customerPaymentsJournals](../api/dynamics_customerpaymentsjournal_delete.md)|none                     |Deletes a customer payments journal.|

## Properties
| Property	         | Type	                 |Description                                                             |
|:-------------------|:----------------------|:-----------------------------------------------------------------------|
|id                  |GUID                   |The unique ID of the customer payments journal. Non-editable.           |
|code                |string, maximum size 10| The code of the customer payments journal.                             |
|displayName         |string, maximum size 50| The display name of the customer payments journal.                     |
|lastModifiedDateTime|datetime               |The last datetime the customer payments journal was modified. Read-Only.|

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
