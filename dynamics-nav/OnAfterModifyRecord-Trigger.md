---
title: "OnAfterModifyRecord Trigger"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 5471bdd5-60fb-44fa-b6bf-96d776714be6
caps.latest.revision: 5
manager: terryaus
---
# OnAfterModifyRecord Trigger
Executed after a record has been modified.  
  
## Applies To  
 XMLports  
  
## Remarks  
 This trigger is used when you import data from an XMLport and then update an existing record in a table with the data from the XMLport.  
  
 If the [AutoSave Property](../dynamics-nav/AutoSave-Property.md) is **No**, then although the record is not modified automatically, the OnAfterModifyRecord trigger is still called after the modification would have occurred.  
  
## See Also  
 [OnAfterInsertRecord Trigger](../dynamics-nav/OnAfterInsertRecord-Trigger.md)   
 [OnBeforeModifyRecord Trigger](../dynamics-nav/OnBeforeModifyRecord-Trigger.md)   
 [OnBeforeInsertRecord Trigger](../dynamics-nav/OnBeforeInsertRecord-Trigger.md)   
 [AutoReplace Property](../dynamics-nav/AutoReplace-Property.md)   
 [AutoSave Property](../dynamics-nav/AutoSave-Property.md)   
 [AutoUpdate Property](../dynamics-nav/AutoUpdate-Property.md)