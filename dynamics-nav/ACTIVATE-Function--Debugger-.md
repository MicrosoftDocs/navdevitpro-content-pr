---
title: "ACTIVATE Function (Debugger)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 620f0e32-eadc-43e9-8f6e-8fc0b12c3aaf
caps.latest.revision: 9
manager: terryaus
---
# ACTIVATE Function (Debugger)
Activates the debugger and attaches the debugger to the next session that is started.  
  
## Syntax  
  
```  
[Ok :=] ACTIVATE  
```  
  
## Property Value\/Return Value  
 Type: Boolean  
  
 **true** if the debugger is started successfully; otherwise, **false**.  
  
 If you omit this optional return value and if the break is not set successfully, then a run\-time error occurs. If you include the return value, then you must handle any errors.  
  
## Remarks  
 The **ACTIVATE** function behaves like the **Debug Next** action on the **Sessions** page.  
  
 You can call either the **ACTIVATE** function or the [ATTACH Function \(Debugger\)](../dynamics-nav/ATTACH-Function--Debugger-.md) to activate the debugger.  
  
 The **ACTIVATE** function is not supported by the [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)]. If the **ACTIVATE** function is called from a page in the [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)], you receive a runtime error with a message that is similar to the following:  
  
 **The Ribbon Tab with id: "MBSCC.1A7.1A7" has not been made available for this page or does not exist. Use Ribbon.MakeTabAvailable\(\).**  
  
## See Also  
 [Activating the Debugger](../dynamics-nav/Activating-the-Debugger.md)   
 [DEACTIVATE Function \(Debugger\)](../dynamics-nav/DEACTIVATE-Function--Debugger-.md)