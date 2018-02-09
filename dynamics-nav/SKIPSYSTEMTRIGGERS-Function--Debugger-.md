---
title: "SKIPSYSTEMTRIGGERS Function (Debugger)"
ms.custom: na
ms.date: 06/04/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 58204e79-338e-44b4-8d56-adc9506b8557
caps.latest.revision: 3
manager: edupont
---
# SKIPSYSTEMTRIGGERS Function (Debugger)
Enables the debugger to skip code that is inside system triggers.  
  
## Syntax  
  
```  
[Ok :=] SKIPSYSTEMTRIGGERS(Ok)   
```  
  
#### Parameters  
 *Ok*  
 Type: Boolean  
  
 Specifies if the debugger should skip system triggers.  
  
## Property Value/Return Value  
 Type: Boolean  
  
 **true** if the debugger skips system triggers; otherwise, **false**.  
  
 If you omit this optional return value and if the break is not set successfully, then a run-time error occurs. If you include the return value, then you must handle any errors.  
  
## See Also  
 [Debugger](Debugger.md)