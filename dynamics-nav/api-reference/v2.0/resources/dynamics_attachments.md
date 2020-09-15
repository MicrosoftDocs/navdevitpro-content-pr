---
title: attachments resource type | Microsoft Docs
description: A attachments object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/15/2020
ms.author: solsen
---

# attachments resource type
Represents an attachments in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods
| Method | Return Type|Description |
|:--------------------|:-----------|:-------------------------|
|[DELETE attachments](../api/dynamics_attachments_Delete.md)|attachments|Deletes a attachments object.|
|[POST attachments](../api/dynamics_attachments_Create.md)|attachments|Creates a attachments object.|
|[PATCH attachments](../api/dynamics_attachments_Update.md)|attachments|Updates a attachments object.|




## Navigation

| Navigation |Return Type| Description |    
|:----------|:----------|:-----------------|
|[salesInvoice](../resources/dynamics_salesinvoice.md)|salesInvoice |Gets the salesinvoice of the attachments.|
|[journalLine](../resources/dynamics_journalline.md)|journalLine |Gets the journalline of the attachments.|
|[generalLedgerEntry](../resources/dynamics_generalledgerentry.md)|generalLedgerEntry |Gets the generalledgerentry of the attachments.|
|[salesOrder](../resources/dynamics_salesorder.md)|salesOrder |Gets the salesorder of the attachments.|
|[salesQuote](../resources/dynamics_salesquote.md)|salesQuote |Gets the salesquote of the attachments.|
|[salesCreditMemo](../resources/dynamics_salescreditmemo.md)|salesCreditMemo |Gets the salescreditmemo of the attachments.|
|[purchaseInvoice](../resources/dynamics_purchaseinvoice.md)|purchaseInvoice |Gets the purchaseinvoice of the attachments.|


## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|id|GUID|The unique ID of the item. Non-editable.|
|parentId|GUID|The ID of the parent entity. |
|fileName|string|Logical filename.|
|byteSize|integer|File size.|
|attachmentContent|stream|The attachment's content.|
|lastModifiedDateTime|datetime|The last datetime the attachments was modified. Read-Only.|
|parentType|string|The type of the parent document of the attachments.|


## JSON representation

Here is a JSON representation of the attachments resource.


```json
{
   "id": "GUID",
   "parentId": "GUID",
   "fileName": "string",
   "byteSize": "integer",
   "attachmentContent": "stream",
   "lastModifiedDateTime": "datetime",
   "parentType": "string"
}
```
## See also

[DELETE attachments](../api/dynamics_attachments_Delete.md)
[POST attachments](../api/dynamics_attachments_Create.md)
[PATCH attachments](../api/dynamics_attachments_Update.md)

