---
title: "OnBeforeInsertRecord Trigger"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 45f257ec-9ff2-4797-906b-2daef5784556
caps.latest.revision: 9
manager: edupont
---
# OnBeforeInsertRecord Trigger
Executed after a record has been loaded and before it is inserted into a database table.  
  
## Applies To  
 XMLports  
  
## Remarks  
 This trigger is only used to import data. It is typically used for evaluation or calculations before the record is inserted into the database table.  
  
 If the [AutoSave Property](AutoSave-Property.md) is **No**, then although the record is not inserted automatically, the OnBeforeInsertRecord trigger is still called before the insertion would have occurred.  
  
## See Also  
 [Triggers](Triggers.md)