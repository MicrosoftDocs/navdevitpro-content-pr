---
title: "Extending Microsoft Dynamics NAV Using Microsoft .NET Framework Interoperability"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: a50931c9-ec89-4ce9-aabf-285fec341c69
caps.latest.revision: 11
manager: terryaus
---
# Extending Microsoft Dynamics NAV Using Microsoft .NET Framework Interoperability
You can extend the [!INCLUDE[rtc](../dynamics-nav/includes/rtc_md.md)]s and [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] with functionality that is available in Microsoft .NET Framework assemblies. You can take advantage of .NET Framework interoperability so that [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] objects can interact with .NET Framework objects. In your [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] objects, you can reference .NET Framework assemblies and call their members directly from C\/AL code. You can use assemblies from the .NET Framework class library, which are found in the global assembly cache; your own custom assemblies; or third\-party assemblies. For more information, see [Assembly Installation in the GAC](http://go.microsoft.com/fwlink/?LinkID=196848).  
  
 .NET Framework interoperability offers an alternative to COM so that you can extend your solution. For example, you can use .NET Framework interoperability to:  
  
-   Consume web services.  
  
-   Integrate with Microsoft Office products.  
  
-   Create .NET Framework applications that target the [!INCLUDE[rtc](../dynamics-nav/includes/rtc_md.md)].  
  
## [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)] support  
 For the [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)], you can only implement Microsoft .NET Framework Interoperability objects that are configured to run on [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)]. Client\-side objects are not supported. For more information, see [Setting .NET Framework Types to Target the Microsoft Dynamics NAV Windows Client or Server](../dynamics-nav/Setting-.NET-Framework-Types-to-Target-the-Microsoft-Dynamics-NAV-Windows-Client-or-Server.md)  
  
## See Also  
 [Calling .NET Framework Members from C\-AL](../dynamics-nav/Calling-.NET-Framework-Members-from-C-AL.md)   
 [Mapping Between .NET Framework and C\-AL Types](../dynamics-nav/Mapping-Between-.NET-Framework-and-C-AL-Types.md)   
 [Using Arrays](../dynamics-nav/Using-Arrays.md)   
 [Using Collections](../dynamics-nav/Using-Collections.md)   
 [Using Enumerations](../dynamics-nav/Using-Enumerations.md)   
 [Using Generics](../dynamics-nav/Using-Generics.md)   
 [Using Interfaces](../dynamics-nav/Using-Interfaces.md)   
 [Calling External Web Services](../dynamics-nav/Calling-External-Web-Services.md)