---
title: "OnBeforeModifyRecord Trigger"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: a21e19e1-25c3-446c-a846-620061f31e99
caps.latest.revision: 3
manager: edupont
---
# OnBeforeModifyRecord Trigger
Executed after a record is read from the input stream and before the existing record in the database is modified.  
  
## Applies To  
 XMLports  
  
## Remarks  
 This trigger is used when you import data from an XMLport and then update an existing record in a table with the data from the XMLport.  
  
 If the [AutoSave Property](AutoSave-Property.md) is **No**, then although the record is not modified automatically, the OnBeforeModifyRecord trigger is still called before the modification would have occurred.  
  
## See Also  
 [OnAfterModifyRecord Trigger](OnAfterModifyRecord-Trigger.md)   
 [OnAfterInsertRecord Trigger](OnAfterInsertRecord-Trigger.md)   
 [OnBeforeInsertRecord Trigger](OnBeforeInsertRecord-Trigger.md)   
 [AutoReplace Property](AutoReplace-Property.md)   
 [AutoSave Property](AutoSave-Property.md)   
 [AutoUpdate Property](AutoUpdate-Property.md)