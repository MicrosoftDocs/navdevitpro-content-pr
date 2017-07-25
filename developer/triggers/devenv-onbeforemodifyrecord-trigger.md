---
title: "OnBeforeModifyRecord Trigger"
description: 
author: SusanneWindfeldPedersen

ms.custom: na
ms.date: 07/07/2017
ms.author: solsen
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-365-financials"
ms.assetid: a21e19e1-25c3-446c-a846-620061f31e99
caps.latest.revision: 3
manager: edupont
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# OnBeforeModifyRecord Trigger
Executed after a record is read from the input stream and before the existing record in the database is modified.  
  
## Applies To  
 XMLports  
  
## Remarks  
 This trigger is used when you import data from an XMLport and then update an existing record in a table with the data from the XMLport.  
  
 If the [AutoSave Property](../properties/devenv-autosave-property.md) is **false**, then although the record is not modified automatically, the OnBeforeModifyRecord trigger is still called before the modification would have occurred.  
  
## See Also  
 [OnAfterModifyRecord Trigger](devenv-onaftermodifyrecord-trigger.md)   
 [OnAfterInsertRecord Trigger](devenv-onafterinsertrecord-trigger.md)   
 [OnBeforeInsertRecord Trigger](devenv-onbeforeinsertrecord-trigger.md)   
 [AutoReplace Property](../properties/devenv-autoreplace-property.md)   
 [AutoSave Property](../properties/devenv-autosave-property.md)   
 [AutoUpdate Property](../properties/devenv-autoupdate-property.md)