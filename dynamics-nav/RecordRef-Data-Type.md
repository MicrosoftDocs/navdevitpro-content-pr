---
title: RecordRef Data Type
description: A RecordRef object references a record in a table. RecordRef object in functions apply to more than one table, not to a specific table. 
ms.custom: na
ms.date: 10/30/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 38be0545-2499-46f6-bfec-77f218ba0045
caps.latest.revision: 9
---
# RecordRef Data Type in Dynamics NAV
A RecordRef object references a record in a table. Typically, you use a RecordRef object in functions that must apply to more than one table, not to a specific table. For example, you could use a RecordRef object in a function that loops through several tables or as a parameter of a function that is called for records of different tables.  
  
 The RecordRef object can refer to any table in the database. Use the [OPEN Function \(RecordRef\)](OPEN-Function--RecordRef-.md) to use the table number to select the table that you want to access, or use the [GETTABLE Function \(RecordRef\)](GETTABLE-Function--RecordRef-.md) to use another record variable to select the table that you want to access.  
  
 If one RecordRef variable is assigned to another RecordRef variable, then they both refer to the same table instance.  
  
## See Also  
 [ADDLINK Function (RecordRef)](ADDLINK-Function--RecordRef-.md)  
 [ASCENDING Function (RecordRef)](ASCENDING-Function--RecordRef-.md)  
 [CAPTION Function (RecordRef)](CAPTION-Function--RecordRef-.md)  
 [CHANGECOMPANY Function (RecordRef)](CHANGECOMPANY-Function--RecordRef-.md)  
 [CLOSE Function (RecordRef)](CLOSE-Function--RecordRef-.md)  
 [COPYLINKS Function (RecordRef)](COPYLINKS-Function--RecordRef-.md)  
 [COUNT Function (RecordRef)](COUNT-Function--RecordRef-.md)  
 [CURRENTCOMPANY Function (RecordRef)](CURRENTCOMPANY-Function--RecordRef-.md)  
 [CURRENTKEY Function (RecordRef)](CURRENTKEY-Function--RecordRef-.md)  
 [CURRENTKEYINDEX Function (RecordRef)](CURRENTKEYINDEX-Function--RecordRef-.md)  
 [DELETE Function (RecordRef)](DELETE-Function--RecordRef-.md)  
 [DELETEALL Function (RecordRef)](DELETEALL-Function--RecordRef-.md)  
 [DELETELINK Function (RecordRef)](DELETELINK-Function--RecordRef-.md)  
 [DELETELINKS Function (RecordRef)](DELETELINKS-Function--RecordRef-.md)  
 [DUPLICATE Function (RecordRef)](DUPLICATE-Function--RecordRef-.md)  
 [FIELD Function (RecordRef)](FIELD-Function--RecordRef-.md)  
 [FIELDCOUNT Function (RecordRef)](FIELDCOUNT-Function--RecordRef-.md)  
 [FIELDEXIST Function (RecordRef)](FIELDEXIST-Function--RecordRef-.md)  
 [FIELDINDEX Function (RecordRef)](FIELDINDEX-Function--RecordRef-.md)  
 [FILTERGROUP Function (RecordRef)](FILTERGROUP-Function--RecordRef-.md)  
 [FIND Function (RecordRef)](FIND-Function--RecordRef-.md)  
 [FINDFIRST Function (RecordRef)](FINDFIRST-Function--RecordRef-.md)  
 [FINDLAST Function (RecordRef)](FINDLAST-Function--RecordRef-.md)  
 [FINDSET Function (RecordRef)](FINDSET-Function--RecordRef-.md)  
 [GET Function (RecordRef)](GET-Function--RecordRef-.md)  
 [GETFILTERS Function (RecordRef)](GETFILTERS-Function--RecordRef-.md)  
 [GETPOSITION Function (RecordRef)](GETPOSITION-Function--RecordRef-.md)  
 [GETTABLE Function (RecordRef)](GETTABLE-Function--RecordRef-.md)  
 [GETVIEW Function (RecordRef)](GETVIEW-Function--RecordRef-.md)  
 [HASFILTER Function (RecordRef)](HASFILTER-Function--RecordRef-.md)  
 [HASLINKS Function (RecordRef)](HASLINKS-Function--RecordRef-.md)  
 [INIT Function (RecordRef)](INIT-Function--RecordRef-.md)  
 [INSERT Function (RecordRef)](INSERT-Function--RecordRef-.md)  
 [ISEMPTY Function (RecordRef)](ISEMPTY-Function--RecordRef-.md)  
 [ISTEMPORARY Function (RecordRef)](ISTEMPORARY-Function--RecordRef-.md)  
 [KEYCOUNT Function (RecordRef)](KEYCOUNT-Function--RecordRef-.md)  
 [KEYINDEX Function (RecordRef)](KEYINDEX-Function--RecordRef-.md)  
 [LOCKTABLE Function (RecordRef)](LOCKTABLE-Function--RecordRef-.md)  
 [MODIFY Function (RecordRef)](MODIFY-Function--RecordRef-.md)  
 [NAME Function (RecordRef)](NAME-Function--RecordRef-.md)  
 [NEXT Function (RecordRef)](NEXT-Function--RecordRef-.md)  
 [NUMBER Function (RecordRef)](NUMBER-Function--RecordRef-.md)  
 [OPEN Function (RecordRef)](OPEN-Function--RecordRef-.md)  
 [RENAME Function (RecordRef)](RENAME-Function--RecordRef-.md)  
 [RECORDID Function (RecordRef)](RECORDID-Function--RecordRef-.md)  
 [READPERMISSION Function (RecordRef)](READPERMISSION-Function--RecordRef-.md)  
 [RESET Function (RecordRef)](RESET-Function--RecordRef-.md)  
 [SETPOSITION Function (RecordRef)](SETPOSITION-Function--RecordRef-.md)  
 [SETVIEW Function (RecordRef)](SETVIEW-Function--RecordRef-.md)  
 [SETTABLE Function (RecordRef)](SETTABLE-Function--RecordRef-.md)  
 [SETRECFILTER Function (RecordRef)](SETRECFILTER-Function--RecordRef-.md)  
 [WRITEPERMISSION Function (RecordRef)](WRITEPERMISSION-Function--RecordRef-.md)
