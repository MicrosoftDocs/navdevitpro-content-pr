---
title: "TYPE Function (FieldRef)"
ms.custom: na
ms.date: 06/04/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 51a69e42-c585-43aa-a85d-81d52a887432
caps.latest.revision: 12
manager: edupont
---
# TYPE Function (FieldRef)
Gets the data type of the field that is currently selected.  
  
## Syntax  
  
```  
  
Type := FieldRef.TYPE  
```  
  
#### Parameters  
 *FieldRef*  
 Type: FieldRef  
  
 Refers to the current field.  
  
## Property Value/Return Value  
 Type: The data type of the field.  
  
## Example  
 The following example opens the Customer table as a RecordRef variable that is named CustomerRecref. The code loops through fields 1 to 5 and creates a FieldRef that is named MyFieldRef for each field that is selected. `MyFieldRef.TYPE` retrieves the data of each field and displays it in a message box. This example requires that you create the following variables and text constant in the **C/AL Globals** windows.  
  
|Variable name|DataType|  
|-------------------|--------------|  
|CustomerRecref|RecordRef|  
|MyFieldRef|FieldRef|  
|varType|Variant|  
  
|Text constant|ENU value|  
|-------------------|---------------|  
|Text000|Field %1 is a %2 data type.|  
  
```  
  
CustomerRecref.OPEN(DATABASE::Customer);  
FOR i := 1 TO 5 DO BEGIN  
  MyFieldRef := CustomerRecref.FIELD(i);  
  MESSAGE(Text000, i, MyFieldRef.TYPE);  
END;  
  
```  
  
## See Also  
 [FieldRef Data Type](FieldRef-Data-Type.md)