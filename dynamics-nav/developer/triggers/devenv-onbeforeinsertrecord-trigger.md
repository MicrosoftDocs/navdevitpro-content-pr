---
title: "OnBeforeInsertRecord Trigger"
ms.custom: na
ms.date: 06/19/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-financials"
ms.assetid: 45f257ec-9ff2-4797-906b-2daef5784556
author: SusanneWindfeldPedersen
manager: edupont
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# OnBeforeInsertRecord Trigger
Executed after a record has been loaded and before it is inserted into a database table.  
  
## Applies To  
 XMLports  
  
## Remarks  
 This trigger is only used to import data. It is typically used for evaluation or calculations before the record is inserted into the database table.  
  
 If the [AutoSave Property](../properties/devenv-autosave-property.md) is **false**, then although the record is not inserted automatically, the OnBeforeInsertRecord trigger is still called before the insertion would have occurred.  
  
## See Also  
 [AutoSave Property](../properties/devenv-autosave-property.md)  
 [Triggers](devenv-triggers.md)  
 [XMLport Triggers](devenv-xmlport-triggers.md)  
 [OnAfterInsertRecord Trigger](devenv-onafterinsertrecord-trigger.md)  