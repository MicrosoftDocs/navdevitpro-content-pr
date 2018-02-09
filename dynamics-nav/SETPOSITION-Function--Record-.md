---
title: "SETPOSITION Function (Record)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 6bdd7e9c-0c48-4977-b0be-618f6118db25
caps.latest.revision: 13
manager: edupont
---
# SETPOSITION Function (Record)
Sets the fields in a primary key on a record to the values specified in the supplied string. The remaining fields are not changed.  
  
## Syntax  
  
```  
  
Record.SETPOSITION(String)  
```  
  
#### Parameters  
 *Record*  
 Type: Record  
  
 The record on which you want to set the primary key field.  
  
 *String*  
 Type: Text or code  
  
 The string that is used to set the primary key. This string contains the primary key value to set.  
  
## Example  
 The following example changes the value in the primary key, the No. field, in table 23, the **Vendor** table. Other fields are not changed. The code starts by opening table 23 as a record variable that is named MyRecord. The [SETRANGE Function \(Record\)](SETRANGE-Function--Record-.md) sets a filter that selects records from 10000 to 20000 in the No. field. The [FINDLAST Function \(RecordRef\)](FINDLAST-Function--RecordRef-.md) finds and retrieves the last record in the record set. The **SETPOSITION** function uses the value stored in the InputString parameter to change the value in the No. field from 20000 to 20001. The record No. and the name of the record are displayed before and displayed again after the primary key value is changed.  The string that contains the new primary key is initialized in the InputString variable. This example requires that you create the following variables and text constants in the **C/AL Globals** window  
  
|Variable name|DataType|Subtype|  
|-------------------|--------------|-------------|  
|InputString|Text|Not applicable|  
|MyRecord|Record|Vendor|  
  
|Text constant name|ConstValue|  
|------------------------|----------------|  
|Text000|The record No. before the primary key was changed is %1.\\ The vendor name before the primary key was changed is %2.|  
|Text001|The record No. after the primary key was changed is %1. \\ The vendor name after the primary key was changed is %2.|  
  
```  
InputString := 'No.=CONST(20001)';  
MyRecord.SETRANGE("No.", '10000','20000');  
MyRecord.FINDLAST;  
MESSAGE(Text000, MyRecord."No.", MyRecord.Name);  
MyRecord.SETPOSITION(InputString);  
MESSAGE(Text001, MyRecord."No.", MyRecord.Name);  
```  
  
 The following is displayed before the **SETPOSITION** function is called:  
  
 **The record No. before the primary key was changed is 20000.**  
  
 **The vendor name before the primary key was changed is AR Day property Management.**  
  
 The following is displayed after the **SETPOSITION** function is called:  
  
 **The record No. after the primary key was changed is 20001.**  
  
 **The vendor name after the primary key was changed is AR Day property Management.**  
  
## See Also  
 [Record Data Type](Record-Data-Type.md)