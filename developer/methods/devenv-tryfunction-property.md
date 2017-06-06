---
title: "TryFunction Property"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 71d0080e-a02c-4545-8bb3-299ad80b1db8
caps.latest.revision: 4
manager: edupont
---
# TryFunction Property
Specifies the method to be try method, which can be used to catch and handle errors and exceptions that occur when code is run.  
  
## Applies to  
 AL methods.  
  
> [!NOTE]  
>  In test and upgrade codeunits, this property only applies to normal methods as specified by the [FunctionType Property \(Test Codeunits\)](devenv-FunctionType-Property--Test-Codeunits.md) or [FunctionType Property \(Upgrade Codeunits\)](devenv-FunctionType-Property--Upgrade-Codeunits.md).  
  
## Remarks  
 Try methods in AL enable you to handle errors that occur in the application during code execution. For example, with try methods, you can provide more user-friendly error messages to the end user than those thrown by the system. You can use try methods to catch errors/exceptions that thrown by [!INCLUDE[d365fin_md](../includes/d365fin_md.md)] or exceptions that are thrown during .NET Framework interoperability operations.  
  
 For more information, see [Handling Errors by Using Try Methods](Handling-Errors-by-Using-Try-Methods.md).  
  
## See Also  
 [AL Method Statements](C-AL-Method-Statements.md)