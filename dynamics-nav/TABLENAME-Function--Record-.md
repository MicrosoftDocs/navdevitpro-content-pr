---
title: "TABLENAME Function (Record)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: a6598c08-aeb0-466e-b5a9-d2374eff813b
caps.latest.revision: 12
manager: pchapman
---
# TABLENAME Function (Record)
Gets the name of a table.  
  
## Syntax  
  
```  
  
Name := Record.TABLENAME  
```  
  
#### Parameters  
 *Record*  
 Type: Record  
  
 The record in the table for which you want to find the table name.  
  
## Property Value\/Return Value  
 Type: Text or code  
  
 The name of the table.  
  
## Remarks  
 The [TABLECAPTION Function \(Record\)](../dynamics-nav/TABLECAPTION-Function--Record-.md) retrieves the [Caption Property\-duplicate](../dynamics-nav/Caption-Property-duplicate.md) of the table. If you want to enable your application for multilanguage functionality now or in the future, you must use the **TABLECAPTION** function instead of the **TABLENAME** function.  
  
## Example  
 The following example retrieves the name of the **Customer** table by using the CustomerRec variable, a record from the **Customer** table. The value of the **Customer** table name is stored in the TableName variable and displayed in a message box. The value that is displayed is Customer.  
  
 This example requires that you create the following variables in the **C\/AL Globals** window.  
  
|Variable name|DataType|Subtype|  
|-------------------|--------------|-------------|  
|CustomerRec|Record|Customer|  
|TableName|Text|Not applicable|  
  
```  
TableName := CustomerRec.TABLENAME;  
MESSAGE('The name of the table is: %1', TableName);  
```  
  
## See Also  
 [Record Data Type](../dynamics-nav/Record-Data-Type.md)   
 [Multilanguage Development](../dynamics-nav/Multilanguage-Development.md)