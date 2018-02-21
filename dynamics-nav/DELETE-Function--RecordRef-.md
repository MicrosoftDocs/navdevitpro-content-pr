---
title: "DELETE Function (RecordRef)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 365091c9-fe6c-464c-9917-02c7cf13a72f
caps.latest.revision: 15
manager: edupont
---
# DELETE Function (RecordRef)
Deletes a record in a table.  
  
## Syntax  
  
```  
  
[Ok :=] RecordRef.DELETE([RunTrigger])  
```  
  
#### Parameters  
 *RecordRef*  
 Type: RecordRef  
  
 The RecordRef that refers to the record that you want to delete.  
  
> [!WARNING]  
>  The record cannot be from table 2000000001, the Object table or table 2000000006, the Company table.  
  
 *RunTrigger*  
 Type: Boolean  
  
 Specifies whether the code in the **OnDelete** trigger will be executed. If this parameter is **true**, the code will be executed. If this parameter is **false**, then the code in the **OnDelete** trigger is not executed.  
  
 The default value is **false**.  
  
 This parameter is optional.  
  
## Property Value/Return Value  
 Type: Boolean  
  
 **true** if the record was deleted. **false** if the record was not deleted because it could not be found in the table, because the user did not have the correct permissions, or because the C/AL code terminated.  
  
 If the record is not deleted and you do not include a return value, then a run-time error occurs. If you include the return value, then you must handle any errors.  
  
## Remarks  
 The current key and any filters on the record do not affect this operation. The record to delete is identified by the values in its primary key.  
  
 If an end-user modifies a record between the time that another end-user or another process reads the record and modifies it, then the second user must refresh the value of the record variable before editing the record. Otherwise, the end-user receives the following run-time error:  
  
 **Another user has modified the record for this \<Table Name> after you retrieved it from the database.**  
  
 **Enter your changes again in the updated window, or start the interrupted activity again.**  
  
 In earlier versions of [!INCLUDE[navnow](includes/navnow_md.md)], certain situations allowed code that an end-user runs to modify a record after a newer version of the record was written and committed to the database. This would overwrite the newer changes. However, in [!INCLUDE[navnowlong](includes/navnowlong_md.md)], we have restricted the [MODIFY Function \(RecordRef\)](MODIFY-Function--RecordRef-.md), [RENAME Function \(RecordRef\)](RENAME-Function--RecordRef-.md), and **DELETE** Function \(RECORDREF\) so that the end-user receives the following run-time error in these certain situations:  
  
 **Unable to change an earlier version of the \<Table Name> record. The record should be read from the database again. This is a programming error.**  
  
 You must design your application so that you use the most up-to-date version of the record for modifications to the database. You use the [GET Function \(RecordRef\)](GET-Function--RecordRef-.md) to refresh the record with the latest version.  
  
## Example  
 The following example deletes a record from the Customer table. The code starts by opening the **Customer** table \(18\) as a RecordRef variable that is named MyRecordRef. The [FIELD Function \(RecordRef\)](FIELD-Function--RecordRef-.md) creates a FieldRef that is named MyFieldRef for field 1, which is the primary key of the **Customer** table. The [VALUE Function \(FieldRef, TestPage Field\)](VALUE-Function--FieldRef--TestPage-Field-.md) assigns the value 10000 to the field that the MyFieldRef variable refers to. The [FIND Function \(RecordRef\)](FIND-Function--RecordRef-.md) searches the table for a record with field 1 = 10000. If the record is found, then it is deleted, the table is modified, and a message is displayed. This example requires that you create the following variables and text constant in the **C/AL Globals** window.  
  
|Variable name|DataType|  
|-------------------|--------------|  
|varRecordToDelete|Code|  
|MyRecordRef|RecordRef|  
|MyFieldRef|FieldRef|  
  
|Text constant name|ConstValue|  
|------------------------|----------------|  
|Text000|Customer %1 is deleted.|  
  
```  
varRecordToDelete := '10000';  
MyRecordRef.OPEN(18);  
MyFieldRef := MyRecordRef.FIELD(1);  
MyFieldRef.VALUE := varRecordToDelete;  
IF MyRecordRef.FIND('=') THEN BEGIN  
  IF MyRecordRef.DELETE THEN BEGIN  
    MyRecordRef.MODIFY;  
    MESSAGE(Text000, MyFieldRef.VALUE);  
  END;  
END;  
  
```  
  
## See Also  
 [RecordRef Data Type](RecordRef-Data-Type.md)   
 [OnDelete Trigger](OnDelete-Trigger.md)