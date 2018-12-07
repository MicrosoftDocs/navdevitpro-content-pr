---
title: "TableNo Property"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: e28a2f89-b24f-4191-aa37-12d3a9901b88
caps.latest.revision: 7
manager: edupont
---
# TableNo Property

Sets a record parameter by reference to the table on the `OnRun` trigger.
  
## Applies To  
 Codeunits  
  
## Remarks  

Setting the **TableNo** property changes the signature of the `OnRun` trigger of the codeunit to include a variable `Record` data type parameter (named `Rec`) for the specified table. For example, if you set the **TableNo** property to the **Item** table, the OnRun trigger signature will change to the following.

`OnRun(var Rec : Record Item)`

 If you specify a table number for this property, then you can use `Rec` in the code and use the [Codeunit.RUN Function \(Codeunit\)](Codeunit.RUN-Function--Codeunit-.md) to execute the code unit.  
 
Use the lookup to select the appropriate table number. If the codeunit can apply to any table, then choose Undefined.  
  

  
## See Also  
 [Codeunit.RUN Function \(Codeunit\)](Codeunit.RUN-Function--Codeunit-.md)