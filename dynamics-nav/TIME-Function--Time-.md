---
title: "TIME Function (Time)"
description: This article describes how the TIME function (Time) gets the current time from the operating system.
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: d670fe72-94d5-43b8-bb4b-4b48805b16c9
caps.latest.revision: 9
manager: edupont
---
# TIME Function (Time)
Gets the current time from the operating system.  
  
## Syntax  
  
```  
  
Time := TIME  
```  
  
## Property Value/Return Value  
 Type: Time  
  
 The current time.  
  
## Remarks  
The time that is returned is different for the [!INCLUDE[nav_windows](includes/nav_windows_md.md)] and [!INCLUDE[nav_web](includes/nav_web_md.md)]. For the Windows client, TIME returns the current time of the computer that is running the client, as determined by the date and time settings of the operating system. For the Web client, the day is determined by the Regional Setting that is set in the client.  


You can only use the TIME function to retrieve the time from the operating system. You cannot use it to set the time in the operating system.  
  
## Example
  
This example requires that you create the following text constant in the **C/AL Globals** window.  
  
|Name|ConstValue|  
|----------|----------------|  
|Text000|The current system time is %1.|  
  
```  
MESSAGE(Text000, TIME);  
```  
  
 On a computer that has the regional format set to English \(United States\), the message window could display the following:  
  
 **The current system time is 11:15:46 AM.**  
  
## See Also  
 [Time Data Type](Time-Data-Type.md)   
 [Date and Time Functions](Date-and-Time-Functions.md)