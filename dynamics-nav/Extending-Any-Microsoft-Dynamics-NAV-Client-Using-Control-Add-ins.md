---
title: "Extending Any Microsoft Dynamics NAV Client Using Control Add-ins"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 117009ff-718f-47ba-bade-175481a0ca94
caps.latest.revision: 10
---
# Extending Any Microsoft Dynamics NAV Client Using Control Add-ins
With [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] you can write control add\-ins that add custom functionality to Role Centers and pages on all display targets, using the same extensibility framework. The following sections provide an overview of the documentation that is available to develop and use control add\-ins.  
  
 Control add\-ins that are designed with [!INCLUDE[navsicily](../dynamics-nav/includes/navsicily_md.md)], [!INCLUDE[navcrete](../dynamics-nav/includes/navcrete_md.md)], or [!INCLUDE[navcorfu](../dynamics-nav/includes/navcorfu_md.md)] using a .NET 4.5 assembly and a manifest file, can be used on all display targets. Control add\-ins that were written for earlier versions, will still run on the [!INCLUDE[nav_windows](../dynamics-nav/includes/nav_windows_md.md)].  
  
> [!NOTE]  
>  Javascript\-based client add\-ins in repeater controls, such as lists, listparts, list subpages, and worksheets, are not supported on any of the [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] clients.  
  
## Getting an Overview of Client Control Add\-ins  
  
|To|See|  
|--------|---------|  
|Get a general overview about client control add\-ins and where they fit in the [!INCLUDE[navnowlong](../dynamics-nav/includes/navnowlong_md.md)] architecture.|[Extending Any Microsoft Dynamics NAV Client Using Control Add\-ins](../dynamics-nav/Extending-Any-Microsoft-Dynamics-NAV-Client-Using-Control-Add-ins.md)|  
|Go through an example of how to implement a simple control add\-in, creating a .NET assembly, a manifest file, and a page to display the control add\-in from.|[Walkthrough: Creating and Using a Client Control Add\-in](../Topic/Walkthrough:%20Creating%20and%20Using%20a%20Client%20Control%20Add-in.md)|  
|Review an example of a manifest file.|[Manifest Overview](../dynamics-nav/Manifest-Overview.md)|  
|Get reference Help on the available methods for the extensibility framework.|[InvokeExtensibilityMethod Method](../dynamics-nav/InvokeExtensibilityMethod-Method.md), [GetImageResource Method](../dynamics-nav/GetImageResource-Method.md), and [GetEnvironment Method](../dynamics-nav/GetEnvironment-Method.md).|  
  
## See Also  
 [\($ S\_2150 Control Add\-ins $\)](../dynamics-nav/-$-S_2150-Control-Add-ins-$-.md)   
 [Developing for the Microsoft Dynamics NAV Universal App](../dynamics-nav/Developing-for-the-Microsoft-Dynamics-NAV-Universal-App.md)   
 [Developing for the Microsoft Dynamics NAV Web Client](../dynamics-nav/Developing-for-the-Microsoft-Dynamics-NAV-Web-Client.md)