---
title: "SETSELECTIONFILTER Function"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 1fee3659-dec1-4ae9-b9cd-d6ae4bd89050
caps.latest.revision: 7
manager: edupont
---
# SETSELECTIONFILTER Function
Notes the records that the user has selected on the page, marks those records in the table specified, and sets the filter to "marked only".  
  
## Syntax  
  
```  
  
CurrPage.SETSELECTIONFILTER(Record)  
```  
  
#### Parameters  
 *Record*  
 Type: Record  
  
 A specific record or records.  
  
## Remarks  
 If all records are selected, marks will not be used.  
  
 If only the current record is selected on the page, then SetSelectionFilter does the following:  
  
-   Sets the current filter group to 0 on the destination record  
  
-   Adds filters on the primary key fields that point to the current record of the page  
  
 If more than one record is selected on the page, then SetSelectionFilter does the following:  
  
-   Copies the current key from the page source table to the destination record  
  
-   Copies the current sort order from the table to the destination record  
  
-   Copies the current filters that are set in all filter groups  
  
-   Copies the current filter group  
  
-   Marks the selected records and sets the "marked only" filter  
  
## See Also  
 [Page Data Type](Page-Data-Type.md)