---
title: "OnRename Trigger"
ms.custom: na
ms.date: 06/19/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-365-financials"
ms.assetid: f3b559c5-98d1-4880-9c36-cbff899ff993
caps.latest.revision: 3
manager: edupont
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# OnRename Trigger
Executed when a user tries to rename a record.  
  
## Applies to  
 Tables  
  
## Remarks  
 When you rename a record in one location, it is updated in all other locations. The OnRename trigger executes before the rename occurs. The record is not renamed if an error occurs in the trigger code.  
  
## See Also  
 [Triggers](devenv-triggers.md)  
 [Table and Field Triggers](devenv-table-and-field-triggers.md)  