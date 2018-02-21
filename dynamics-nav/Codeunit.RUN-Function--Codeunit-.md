---
title: "Codeunit.RUN Function (Codeunit)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 1af95284-90c8-4e79-9037-1ca9e4327ac7
caps.latest.revision: 15
---
# Codeunit.RUN Function (Codeunit)
Loads and executes the unit of C/AL code that you specify. See also [RUN Function \(Codeunit\)](RUN-Function--Codeunit-.md).  
  
## Syntax  
  
```  
  
[Ok :=] Codeunit.RUN(Number[, Record])  
```  
  
#### Parameters  
 *Number*  
 Type: Integer  
  
 The ID of the codeunit to run. You can use the **Symbols** option on the **View** menu to select from a list.  
  
 You can specify the codeunit by name instead of by ID by using the following syntax:  
  
 Codeunit.RUN\(CODEUNIT::"\<*codeunit name*>", *RecVariable*\)  
  
 If the codeunit that you specify does not exist, then a run-time error occurs.  
  
 If you run the codeunit with a record from a table other than the one it is associated with in the [TableNo Property](TableNo-Property.md) of the codeunit, then a run-time error occurs.  
  
 *Record*  
 Type: Record  
  
 Specifies a record from the table that is associated with the codeunit in the **TableNo** property.  
  
## Property Value/Return Value  
 Type: Boolean  
  
 If you do not include the optional return value and an error occurs when the codeunit is running, then the C/AL code that called this codeunit will end.  
  
 If you include the return value and an error occurs, then the calling C/AL code continues to run. This means that you must handle any errors.  
  
 **true** if no errors occurred; otherwise, **false**.  
  
## Example  
 The following example runs codeunit 15, Gen. Jnl.-Show Card by specifying the ID. This codeunit is associated with the Gen. Journal Line table. This example requires that you create the following variable in the **C/AL Globals** window.  
  
|Variable name|DataType|Subtype|  
|-------------------|--------------|-------------|  
|GenJournalLine|Record|Gen. Journal Line|  
  
```  
CODEUNIT.RUN(15,GenJournalLine);  
```  
  
## Example  
 The following example runs codeunit 15, Gen. Jnl.-Show Card by specifying the name of the codeunit instead of the ID. This example requires that you create the following variable in the **C/AL Globals** window.  
  
|Variable name|DataType|Subtype|  
|-------------------|--------------|-------------|  
|GenJournalLine|Record|Gen. Journal Line|  
  
```  
CODEUNIT.RUN(CODEUNIT::"Gen. Jnl.-Show Card",GenJournalLine);  
```  
  
## See Also  
 [Codeunit Data Type](Codeunit-Data-Type.md)