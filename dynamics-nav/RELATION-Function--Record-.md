---
title: "RELATION Function (Record)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 7ffa1126-0203-4d68-9298-8d7871f100b6
caps.latest.revision: 10
manager: edupont
---
# RELATION Function (Record)
Determines the table relationship of a given field.  
  
## Syntax  
  
```  
  
TableNumber := Record.RELATION(Field)  
```  
  
#### Parameters  
 *Record*  
 Type: Record  
  
 The record that contains *Field*.  
  
 *Field*  
 Type: Field  
  
 The field for which you want to find the table relationship.  
  
## Property Value/Return Value  
 Type: Integer  
  
 The number of the table that has a relationship with *Field*. This relationship is set up through the properties.  
  
## Remarks  
 You can use this function for several purposes, such as to determine lookups or to check if you have permission to read from a table.  
  
## Example  
 The following example displays the number of the table that has a relation with the City field in the **Customer** table. In this example, table number 225, the **Post Code** table, is displayed because a table relation exists in the City field. If a relation does not exist, then an error message is displayed. This example requires that you create the following variables in the **C/AL Globals** window.  
  
|Variable name|DataType|Subtype|  
|-------------------|--------------|-------------|  
|CustomerRec|Record|Customer|  
|varTableNumber|Integer|Not applicable|  
  
```  
varTableNumber := CustomerRec.RELATION (CustomerRec.City);  
MESSAGE('%1', varTableNumber);  
```  
  
## See Also  
 [Record Data Type](Record-Data-Type.md)