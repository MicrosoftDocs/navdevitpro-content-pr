---
title: "WRITEPERMISSION Function (Record)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 89baebc9-7d28-42b9-b8ad-cb3ca760fad2
caps.latest.revision: 11
manager: edupont
---
# WRITEPERMISSION Function (Record)
Determines whether a user can write to a table. This function can test for both full write permission and partial write permission that has been granted with a security filter. A write permission consists of Insert, Delete, and Modify permissions.  
  
## Syntax  
  
```  
  
Ok := Record.WRITEPERMISSION  
```  
  
#### Parameters  
 *Record*  
 Type: Record  
  
 A record in the table from which you want to determine if you have write permission.  
  
## Property Value/Return Value  
 Type: Boolean  
  
 Specifies whether you have permission to write to the table using any of the following record functions:  
  
-   [INSERT Function \(Record\)](INSERT-Function--Record-.md)  
  
-   [DELETE Function \(Record\)](DELETE-Function--Record-.md)  
  
-   [MODIFY Function \(Record\)](MODIFY-Function--Record-.md)  
  
-   [RENAME Function \(Record\)](RENAME-Function--Record-.md)  
  
-   [DELETEALL Function \(Record\)](DELETEALL-Function--Record-.md)  
  
-   [MODIFYALL Function \(Record\)](MODIFYALL-Function--Record-.md)  
  
 **true** if you can write to some or all of the table. **false** if you cannot write to the table.  
  
## Remarks  
 This function uses the filter that is currently applied to the *Record* to determine whether you have write permission. If no filter is applied, the function tests for full write permission. If a filter has been set, the function only tests for write permission within the range of the filter.  
  
 To determine whether the user has a partial read permission, because a security filter has been applied, view the **Permissions** page. For more information, see [How to: Set Security Filters](How-to--Set-Security-Filters.md).  
  
 If you do not have permission to write to a table and you attempt to write, a run-time error occurs. This function allows you to determine in advance if you have write permission. When the permissions are checked, the combination of permissions in the license file and the user's permissions in the Permission table is considered.  
  
## Example  
 The following example uses a record from the Vendor table to check whether the user is granted write permission to the Vendor table. The return value from the WRITEPERMISSION function is stored in the varHasWrite variable and displayed in a message box. The value, **Yes** is displayed because the user can write to the Vendor table. This example requires that you create the following variables in the **C/AL Globals** window.  
  
|Variable name|DataType|Subtype|  
|-------------------|--------------|-------------|  
|MyRecord|Record|Vendor|  
|varHasWrite|Boolean|Not applicable|  
  
```  
  
MyRecord.GET('10000');  
varHasWrite := MyRecord.WRITEPERMISSION;  
MESSAGE('Table has Write permission? %1', varHasWrite);  
```  
  
## See Also  
 [Record Data Type](Record-Data-Type.md)