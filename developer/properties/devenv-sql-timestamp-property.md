---
title: "SQL Timestamp Property"
ms.custom: na
ms.date: 06/14/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 615d15ba-5d0e-4071-bfa2-c262c1dccbf4
caps.latest.revision: 3
manager: edupont
---
# SQL Timestamp Property
Specifies a field to be a timestamp field.  

## Applies To  
 Table Fields  

## Property Value  
 **True** if the field is the timestamp field; otherwise, **false**. The default value is **false**.  

## Remarks  
 Each table in [!INCLUDE[d365fin_long_md](../includes/d365fin_long_md.md)] includes a hidden timestamp field. The timestamp field contains row version numbers for records as maintained in SQL Server. This property exposes the timestamp field in the table object, and enables you to write code against it.  

 For more information, see [How to: Use a Timestamp Field](How-to--Use-a-Timestamp-Field.md).  

## See Also  
 [Tables](Tables.md)
