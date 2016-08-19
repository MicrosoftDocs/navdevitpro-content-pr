---
title: "Installing and Configuring Windows Client Control Add-ins on Pages"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: c384ba35-7fed-4dd3-b1e1-4a8346436f3c
caps.latest.revision: 16
manager: terryaus
---
# Installing and Configuring Windows Client Control Add-ins on Pages
In the [!INCLUDE[nav_windows](../dynamics-nav/includes/nav_windows_md.md)], control add\-ins add custom controls or visual elements, on Windows client page fields for displaying and editing data. When a control add\-in is developed, it is compiled into a .NET Framework–based assembly, which is .dll file. To use a control add\-in on [!INCLUDE[nav_windows](../dynamics-nav/includes/nav_windows_md.md)] pages, you must install and configure the control add\-in assembly in the [!INCLUDE[nav_windows](../dynamics-nav/includes/nav_windows_md.md)] environment, which is divided between two tiers: [!INCLUDE[nav_windows](../dynamics-nav/includes/nav_windows_md.md)] and [!INCLUDE[navnowlong](../dynamics-nav/includes/navnowlong_md.md)] SQL server database.  
  
 ![RoleTailored client control add&#45;in installation](../dynamics-nav/media/NAVRTCControlAddinInstall.png "NAVRTCControlAddinInstall")  
  
 The following table outlines the tasks that you must perform on each tier.  
  
|Tier|Tasks|For more information, see|  
|----------|-----------|-------------------------------|  
|[!INCLUDE[nav_windows](../dynamics-nav/includes/nav_windows_md.md)] computer|Install the control add\-in assemblies.|[How to: Install a Windows Client Control Add\-in Assembly](../Topic/How%20to:%20Install%20a%20Windows%20Client%20Control%20Add-in%20Assembly.md)|  
|SQL database|Use the [!INCLUDE[nav_dev_long](../dynamics-nav/includes/nav_dev_long_md.md)] to:<br /><br /> 1.  Register the control add\-ins that are found in the assemblies in the **Client Add\-in** table.<br />2.  Set up control add\-ins on pages.|[How to: Register a Windows Client Control Add\-in](../Topic/How%20to:%20Register%20a%20Windows%20Client%20Control%20Add-in.md)<br /><br /> [How to: Set Up a Windows Client Control Add\-in on a Page](../Topic/How%20to:%20Set%20Up%20a%20Windows%20Client%20Control%20Add-in%20on%20a%20Page.md)|  
  
## See Also  
 [Developing Windows Client Control Add\-ins](../dynamics-nav/Developing-Windows-Client-Control-Add-ins.md)   
 [Windows Client Control Add\-in Overview](../dynamics-nav/Windows-Client-Control-Add-in-Overview.md)   
 [Walkthrough: Creating and Using a Windows Client Control Add\-in](../Topic/Walkthrough:%20Creating%20and%20Using%20a%20Windows%20Client%20Control%20Add-in.md)