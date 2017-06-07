---
title: "OnAfterModifyRecord Trigger"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-365-financials"
ms.assetid: 5471bdd5-60fb-44fa-b6bf-96d776714be6
caps.latest.revision: 5
manager: edupont
---
# OnAfterModifyRecord Trigger
Executed after a record has been modified.  

## Applies To  
 XMLports  

## Remarks  
 This trigger is used when you import data from an XMLport and then update an existing record in a table with the data from the XMLport.  

 If the [AutoSave Property](../devenv-AutoSave-Property.md) is **No**, then although the record is not modified automatically, the OnAfterModifyRecord trigger is still called after the modification would have occurred.  

## See Also  
 [OnAfterInsertRecord Trigger](devenv-OnAfterInsertRecord-Trigger.md)   
 [OnBeforeModifyRecord Trigger](devenv-OnBeforeModifyRecord-Trigger.md)   
 [OnBeforeInsertRecord Trigger](devenv-OnBeforeInsertRecord-Trigger.md)   
 [AutoReplace Property](../devenv-AutoReplace-Property.md)   
 [AutoSave Property](../devenv-AutoSave-Property.md)   
 [AutoUpdate Property](../devenv-AutoUpdate-Property.md)
