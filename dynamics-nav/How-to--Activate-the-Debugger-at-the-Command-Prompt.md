---
title: "How to: Activate the Debugger at the Command Prompt"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: c5f399ab-ddcc-4f88-9f77-c7cc898e8ffb
caps.latest.revision: 19
manager: edupont
---
# How to: Activate the Debugger at the Command Prompt
You can activate the debugger at the command prompt. After you activate the debugger and attach it to a session, program flow in that session continues normally until a breakpoint is hit. For more information, see [Breakpoints](Breakpoints.md).  
  
### To activate the debugger at the command prompt  
  
1.  At the command prompt, locate the [!INCLUDE[rtc](includes/rtc_md.md)] directory. The default location on a 32\-bit computer is [!INCLUDE[navnow_install](includes/navnow_install_md.md)]\\RoleTailored Client. The default location on a 64\-bit computer is [!INCLUDE[navnow_x86install](includes/navnow_x86install_md.md)]\\RoleTailored Client.  
  
2.  Enter the following command:  
  
    ```  
    Microsoft.Dynamics.Nav.Client.exe "DynamicsNAV://< Server>[:<port]>/<ServerInstance>/<Company>/debug"  
    ```  
  
3.  In the **Session List** window, do one of the following:  
  
    -   Choose **Debug Next**. The debugger is now active and is waiting to attach to a session.  
  
    -   Select a session, and then choose **Debug**. The debugger is now active and attached to the selected session.  
  
 In the **Debugger** window, you can enable and disable breakpoints, step through lines of code, and view variable and call stack information. For more information, see [Walkthrough: Debugging the Microsoft Dynamics NAV Windows Client](../Topic/Walkthrough:%20Debugging%20the%20Microsoft%20Dynamics%20NAV%20Windows%20Client.md).  
  
## See Also  
 [Activating the Debugger](Activating-the-Debugger.md)   
 [Debugging](Debugging.md)