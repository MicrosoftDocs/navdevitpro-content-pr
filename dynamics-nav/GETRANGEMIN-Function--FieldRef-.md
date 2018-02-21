---
title: "GETRANGEMIN Function (FieldRef)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 7b17984e-546c-4a57-9c5d-5bc146ded1ef
caps.latest.revision: 14
---
# GETRANGEMIN Function (FieldRef)
Gets the minimum value in a range for a field.  
  
## Syntax  
  
```  
  
Value := FieldRef.GETRANGEMIN  
```  
  
#### Parameters  
 *FieldRef*  
 Type: FieldRef  
  
 Refers to the current field.  
  
## Property Value/Return Value  
 Type: Text constant or Code  
  
 Contains the minimum value of the range set for the field referred to by the *FieldRef*.  
  
 The data type of value must match the data type of the field referred to by the *FieldRef*.  
  
## Remarks  
 This function is like the [GETRANGEMIN Function \(Record\)](GETRANGEMIN-Function--Record-.md) function.  
  
## Example  
 The following example opens the Customer table as RecordRef variable, creates a FieldRef for the first field \(No.\) and stores the reference in the MyFieldRef variable. The [SETFILTER Function \(FieldRef\)](SETFILTER-Function--FieldRef-.md) sets a filter that selects records in the range 10000 to 40000 from the No. field. The GETRANGEMIN function retrieves and stores the minimum value that is set in the filter, stores the value in the varMin variable and displays it in a message box. The varMin variable contains 10000 which is the minimum value that is set in the filter. This example requires that you create the following variables and text constant in the **C/AL Globals** windows.  
  
|Variable name|DataType|  
|-------------------|--------------|  
|CustomerRecref|RecordRef|  
|MyFieldRef|FieldRef|  
|varMin|Text|  
  
|Text constant|ENU value|  
|-------------------|---------------|  
|Text000|The minimum value in the filter is %1.|  
  
```  
  
CustomerRecref.OPEN(DATABASE::Customer);  
MyFieldRef := CustomerRecref.FIELD(1);  
MyFieldRef.SETFILTER('10000..40000');  
varMin := MyFieldRef.GETRANGEMIN;  
MESSAGE(Text000, varMin);  
```  
  
## See Also  
 [GETRANGEMAX Function \(Record\)](GETRANGEMAX-Function--Record-.md)   
 [FieldRef Data Type](FieldRef-Data-Type.md)