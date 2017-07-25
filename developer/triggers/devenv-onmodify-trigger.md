---
title: "OnModify Trigger"
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
ms.assetid: 66f54530-7318-4e43-8aea-ca18c04c5d18
caps.latest.revision: 8
manager: edupont
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# OnModify Trigger
Executed when a user modifies an existing record in a table.  
  
## Applies To  
 Tables  
  
## Remarks  
 This trigger is executed before the default modify behavior is executed. If an error occurs in the trigger code, the record changes are canceled.  
  
 We recommend that you do not include code that can stop the user from recording a change in the OnModify trigger on a table. For example, do not include code for displaying error messages. If a user has previously changed the contents of some fields in a record, then these changes must always be accepted by the system.  
  
## See Also  
 [Triggers](devenv-triggers.md)