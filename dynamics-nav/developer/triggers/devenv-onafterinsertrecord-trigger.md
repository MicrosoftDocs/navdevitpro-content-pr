---
title: "OnAfterInsertRecord Trigger"
ms.custom: na
ms.date: 06/19/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-financials"
ms.assetid: 2dd18e75-4bbe-4e88-8f22-a5b064708bfd
author: SusanneWindfeldPedersen
manager: edupont
redirect_url: /dynamics365/business-central/dev-itpro/developer/triggers/devenv-triggers
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# OnAfterInsertRecord Trigger
Executed after a record has been inserted into a database table.  
  
## Applies To  
 XMLports.  
  
## Remarks  
 This trigger is only used to import data and can be used to move data from temporary tables to real tables.  
  
 If the [AutoSave Property](../properties/devenv-autosave-property.md) is **false**, then although the record is not inserted automatically, the OnAfterInsertRecord trigger is still called after the insertion would have occurred.  
  
## See Also  
 [Triggers](devenv-triggers.md)  
 [AutoSave Property](../properties/devenv-autosave-property.md)  
 [XMLport Triggers](devenv-xmlport-triggers.md)  
 [OnBeforeInsertRecord Trigger](devenv-onbeforeinsertrecord-trigger.md)  