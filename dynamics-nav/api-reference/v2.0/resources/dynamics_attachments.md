---
title: attachments resource type | Microsoft Docs
description: An attachment in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# attachments resource type
Represents an attachment in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method                                                                | Return Type      | Description                    |
|:----------------------------------------------------------------------|:-----------------|:-------------------------------|
|[GET attachments](../api/dynamics_attachments_get.md)      |attachments|Gets a Attachment object   |
|[POST attachments](../api/dynamics_create_attachments.md)  |attachments|Creates a Attachment object.|
|[PATCH attachments](../api/dynamics_attachments_update.md) |attachments|Updated a Attachment object.|
|[DELETE attachments](../api/dynamics_attachments_delete.md)|none              |Deletes a Attachment object.|


## Navigation

| Navigation |Return Type| Description |
|:----------|:----------|:-----------------|
|[salesInvoice](../resources/dynamics_salesinvoice.md)|salesInvoice   |Gets the salesinvoice of the attachments.|
|[journalLine](../resources/dynamics_journalline.md)|journalLine   |Gets the journalline of the attachments.|
|[generalLedgerEntry](../resources/dynamics_generalledgerentry.md)|generalLedgerEntry   |Gets the generalledgerentry of the attachments.|
|[salesOrder](../resources/dynamics_salesorder.md)|salesOrder   |Gets the salesorder of the attachments.|
|[salesQuote](../resources/dynamics_salesquote.md)|salesQuote   |Gets the salesquote of the attachments.|
|[salesCreditMemo](../resources/dynamics_salescreditmemo.md)|salesCreditMemo   |Gets the salescreditmemo of the attachments.|
|[purchaseInvoice](../resources/dynamics_purchaseinvoice.md)|purchaseInvoice   |Gets the purchaseinvoice of the attachments.|

## Properties

| Property                | Type    | Description                                               |
|:------------------------|:------|:----------------------------------------------------------|
|documentId               |GUID   |The ID of the parent invoice.                              |


## JSON representation

Here is a JSON representation of the resource.


```json
  "value": [
    {
   "id": "GUID",
   "parentId": "GUID",
   "fileName": "string",
   "byteSize": "integer",
   "attachmentContent": "stream",
   "lastModifiedDateTime": "datetime",
   "parentType": "string"
}
  ]
```

## See also

[Get Attachment](../api/dynamics_attachments_get.md)  
[Create Attachment](../api/dynamics_create_attachments.md)  
[Update Attachment](../api/dynamics_attachments_update.md)  
[Delete Attachment](../api/dynamics_attachments_delete.md)  