---
title: "READPERMISSION Function (Record)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 53f7980f-1d26-44cf-9262-cb27006b5983
caps.latest.revision: 14
---
# READPERMISSION Function (Record)
Determines whether a user is granted read permission to the table that contains a record. This function can test for both full read permission and partial read permission that has been granted with a security filter.  
  
## Syntax  
  
```  
  
Ok := Record.READPERMISSION  
```  
  
#### Parameters  
 *Record*  
 Type: Record  
  
 The record in the table for which you want to check for read access.  
  
## Property Value/Return Value  
 Type: Boolean  
  
 Specifies whether the user is granted read access to the table.  
  
 **true** if you can read from some or the entire table; otherwise, **false**.  
  
## Remarks  
 This function uses the filter that is currently applied to the *Record* to determine whether you have read permission. If no filter is applied, the function tests for full read permission. If a filter has been set, the function only tests for read permission within the range of the filter.  
  
 To determine whether the user has a partial read permission because a security filter has been applied, view the **Permissions** page. For more information, see [How to: Set Security Filters](How-to--Set-Security-Filters.md).  
  
 If you do not have permission to read from a table and you attempt to read, a run-time error occurs. This function allows you to determine in advance if you have read permission. When the permissions are checked, the combination of permissions in the license file and the user's permissions in the **Permission** table is considered.  
  
## Example  
 The following code example retrieves record number 10000 from the Vendor table and stores the record in the MyRecord variable. The **READPERMISSION** function determines whether the user is granted read permission to the Vendor table. The value **Yes** is displayed in the message box because the user can read from the vendor table. This example requires that you create the following variables in the **C/AL Globals** window.  
  
|Variable name|DataType|Subtype|  
|-------------------|--------------|-------------|  
|MyRecord|Record|Vendor|  
|varHasRead|Boolean|Not applicable|  
  
```  
MyRecord.GET('10000');  
varHasRead := MyRecord.READPERMISSION;  
MESSAGE(Is user the granted Read permission? %1', varHasRead);  
```  
  
## See Also  
 [Record Data Type](Record-Data-Type.md)