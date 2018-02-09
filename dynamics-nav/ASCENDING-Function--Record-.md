---
title: "ASCENDING Function (Record)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 427976ca-affe-471b-85e0-0612462bdf0f
caps.latest.revision: 15
manager: edupont
---
# ASCENDING Function (Record)
Gets or sets the order in which the system searches through a table.  
  
## Syntax  
  
```  
  
[IsAscending :=] Record.ASCENDING([SetAscending])  
```  
  
#### Parameters  
 *Record*  
 Type: Record  
  
 The record in the table to search.  
  
 *SetAscending*  
 Type: Boolean  
  
 Specifies the order of the search.  
  
 **true** if the search is to be done in ascending order; otherwise, **false** if the search is to be done in descending order.   
If you do not use this parameter, the function returns the current search order.  
  
## Property Value/Return Value  
 Type: Boolean  
  
 The order in which a search will be done.  
  
 **true** if the search will be done in ascending order; otherwise, **false**.  
  
## Example  
 The following example returns a value that indicates the current search order of the Customer table, to which MyRecord record belongs. The return value is stored in the *IsAscending* variable and displayed in a message box. In this example, the value **Yes** is displayed in the message box, which mean the search order is ascending. This is because the *SetAscending* parameter is not used. This example requires that you create the following variables and text constant in the **C/AL Globals** window.  
  
|Variable name|DataType|Subtype|  
|-------------------|--------------|-------------|  
|MyRecord|Record|Customer|  
|IsAscending|Boolean|Not applicable|  
  
|Text constant name|Data type|ENU value|  
|------------------------|---------------|---------------|  
|Text000|Text|Is the current sort order ascending?:  %1|  
  
```  
  
IsAscending := MyRecord.ASCENDING;  
MESSAGE(Text000, IsAscending);  
```  
  
## Example  
 The following example sets the current sort order to descending by setting the *SetAscending* parameter to **false**. The value displayed in the message box is **No**.  
  
```  
  
IsAscending := MyRecord.ASCENDING(FALSE);  
MESSAGE(Text000, IsAscending);  
```  
  
## See Also  
 [Record Data Type](Record-Data-Type.md)