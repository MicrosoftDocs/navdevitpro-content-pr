---
title: "BREAKONERROR Function (Debugger)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 06af4d30-28de-43e5-acee-5bdb1b3c2785
caps.latest.revision: 5
manager: edupont
---
# BREAKONERROR Function (Debugger)
Sets whether the debugger breaks on errors.  
  
## Syntax  
  
```  
  
[Ok :=] BREAKONERROR(SetBreakOnError)  
```  
  
#### Parameters  
 *SetBreakOnError*  
 Type: Boolean  
  
 Specifies whether the debugger breaks on errors.  
  
## Property Value/Return Value  
 Type: Boolean  
  
 **true** if the break on errors is set successfully; otherwise, **false**.  
  
 If you omit this optional return value and if the break is not set successfully, then a run-time error occurs. If you include the return value, then you must handle any errors.  
  
## Remarks  
 The debugger must be attached to a session when you run the BREAKONERROR function.  
  
## Example  
 This example shows how to implement the code for an action on a page that sets the break on error setting to **true**. You can use this code example in the OnAction trigger of that action. This code example requires that you create a Boolean variable named *Value*.  
  
```  
Value := true;  
DEBUGGER.BREAKONERROR(Value);  
  
```  
  
## See Also  
 [How to: Break on Errors](How-to--Break-on-Errors.md)