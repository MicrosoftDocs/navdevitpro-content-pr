---
title: "FINDLAST Function (Record)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: dd9f9a1d-27b2-4c6d-ba91-d4a2a201f9b7
caps.latest.revision: 9
manager: pchapman
---
# FINDLAST Function (Record)
Finds the last record in a table based on the current key and filter.  
  
## Syntax  
  
```  
  
[Ok :=] Record.FINDLAST  
```  
  
#### Parameters  
 *Record*  
 Type: Record  
  
 If the record was found, it is returned in this parameter and any [FlowFields](../dynamics-nav/FlowFields.md) in the record are set to zero. You must update the FlowFields by using the [CALCFIELDS Function \(Record\)](../dynamics-nav/CALCFIELDS-Function--Record-.md).  
  
 If the record was not found and if you omitted the return value, a run\-time error occurs.  
  
## Property Value\/Return Value  
 Type: Boolean  
  
 **true** if the record was found; otherwise, **false**.  
  
 If you omit this optional return value and the record cannot be found, a run\-time error occurs. If you include a return value, you must handle any errors.  
  
## Remarks  
 This function should be used instead of FIND\('\+'\) when you only need the last record.  
  
 You should only use this function when you explicitly want to find the last record in a table\/set. Do not use this function in combination with REPEAT...UNTIL.  
  
## Example  
 This example requires that you create a Record variable named GLEntryRec for the G\/L Entry table.  
  
```  
// Read the last record only.   
IF GLEntryRec.FINDLAST THEN  
  …  
```  
  
## See Also  
 [FIND Function \(Record\)](../dynamics-nav/FIND-Function--Record-.md)   
 [FINDFIRST Function \(Record\)](../dynamics-nav/FINDFIRST-Function--Record-.md)   
 [FINDSET Function \(Record\)](../dynamics-nav/FINDSET-Function--Record-.md)   
 [Record Data Type](../dynamics-nav/Record-Data-Type.md)