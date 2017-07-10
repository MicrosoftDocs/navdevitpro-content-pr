---
title: "OnBeforeInsertRecord Trigger"
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
ms.assetid: 45f257ec-9ff2-4797-906b-2daef5784556
caps.latest.revision: 9
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
 [Triggers](devenv-triggers.md)