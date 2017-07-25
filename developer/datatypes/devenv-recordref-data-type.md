---
title: "RecordRef Data Type"
description: 
author: SusanneWindfeldPedersen

ms.custom: na
ms.date: 07/07/2017
ms.author: solsen
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 38be0545-2499-46f6-bfec-77f218ba0045
caps.latest.revision: 9
---
# RecordRef Data Type
A RecordRef object references a record in a table. Typically, you use a RecordRef object in methods that must apply to more than one table, not to a specific table. For example, you could use a RecordRef object in a method that loops through several tables or as a parameter of a method that is called for records of different tables.  
  
 The RecordRef object can refer to any table in the database. Use the [OPEN method (RecordRef)](../methods/devenv-open-method-recordref.md) to use the table number to select the table that you want to access, or use the [GETTABLE method (RecordRef)](../methods/devenv-gettable-method-recordref.md) to use another record variable to select the table that you want to access.  
  
 If one RecordRef variable is assigned to another RecordRef variable, then they both refer to the same table instance.  
  
## See Also  
 [FieldRef Data Type](devenv-fieldref-data-type.md)