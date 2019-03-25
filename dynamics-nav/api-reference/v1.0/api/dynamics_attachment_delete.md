---
title: Delete attachment | Microsoft Docs
description: Deletes attachments in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/01/2019
ms.author: solsen
---

# Delete attachments
Deletes attachments in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request
```
DELETE /businesscentral/companies({companyId})/attachments({parentId},{attachmentId})
```

## Request headers

|Header         |Value                     |
|---------------|--------------------------|
|Authorization  |Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```204 No Content``` response code and it deletes the attachment.

## Example

**Request**

Here is an example of the request.

```json
DELETE https://api.businesscentral.dynamics.com/v1.0/api/v1.0/companies({companyId})/attachments({parentId},{attachmentId})
```

**Response** 

No Content.



## See also
[Attachment](../resources/dynamics_attachment.md)  
[Get Attachments](dynamics_attachment_get.md)  
[Create Attachment](dynamics_attachment_create.md)  
[Upload Attachment](dynamics_attachment_patch.md)  
[Delete Attachment](dynamics_attachment_delete.md)  
