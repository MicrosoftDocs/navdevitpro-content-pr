---
title: attachment resource type | Microsoft Docs
description: An attachment in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/01/2019
ms.author: solsen
---

# attachment resource type
Represents an attachment object in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET attachments](../api/dynamics_attachment_get.md)|accounts|Get attachment object.|
|[POST attachments](../api/dynamics_attachment_create.md)|accounts|Create attachment object.|
|[PATCH attachments](../api/dynamics_attachment_patch.md)|accounts|Upload attachment object.|
|[DELETE attachments](../api/dynamics_attachment_delete.md)|accounts|Delete attachment object.|

## Properties

| Property     | Type   |Description|
|:---------------|:--------|:----------|
|id|GUID|Id of the attachment.|
|parentId|GUID|Id of the entity for which the attachment will be associated.|
|fileName|string|Logical filename.|
|byteSize|integer, read-only|File size.|
|lastModifiedDateTime|datetime|The last datetime the entity was modified.|


## Relationships
None

## JSON representation

Here is a JSON representation of the resource.

```json
{
    "parentId": "GUID",
    "id": "GUID",
    "fileName": "string",
    "byteSize": "integer",
    "content@odata.mediaEditLink": "URL",
    "content@odata.mediaReadLink": "URL",
    "lastModifiedDateTime": "datetime"
}
```
## See also

[Get Attachments](../api/dynamics_attachment_get.md)  
[Create Attachment](../api/dynamics_attachment_create.md)  
[Upload Attachment](../api/dynamics_attachment_patch.md)  
[Delete Attachment](../api/dynamics_attachment_delete.md)  

