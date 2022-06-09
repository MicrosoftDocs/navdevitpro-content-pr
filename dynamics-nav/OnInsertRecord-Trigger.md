---
title: "OnInsertRecord Trigger"
description: "This article describes the OnInsertRecord Trigger, which is executed before a new record is inserted into the table."  
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: eb1d2913-5ab8-40db-8790-e5e6b80b6722
caps.latest.revision: 15
manager: edupont
---
# OnInsertRecord Trigger
Executed before a new record is inserted into the table.  
  
## Syntax  
  
```  
  
[Ok]:= OnInsertRecord(BelowxRec)  
```  

### Parameters
 *BelowxRec*  
 
\(Boolean\) Specifies whether the new record is to be inserted after the last record in the table \(xRec\) or not. If **false**, the record is to be inserted between an existing record and the last record. If **true**, the record is to be inserted below the last record in the table \(xRec\).  
  

## Return Value  

 *Ok*  
 \(Boolean\) Determines whether to insert a new record. The return value is checked after each function call. If **true**, the record is inserted. If **false**, the record is not inserted.  
  
## Applies To  
  
-   Pages  
  
## Remarks  
 If an error occurs in the trigger code, the action is canceled, but the page is not closed. The user cannot enter any new data and an error is shown in the message bar.  
  
## See Also  
 [Triggers](Triggers.md)