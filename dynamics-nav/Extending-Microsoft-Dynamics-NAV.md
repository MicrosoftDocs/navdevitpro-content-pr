---
title: "Extending Microsoft Dynamics NAV"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: f81f6fbf-f5ae-498f-9b7b-4f9aa4f369d4
caps.latest.revision: 9
manager: terryaus
---
# Extending Microsoft Dynamics NAV
This section describes how you can extend the functionality of [!INCLUDE[navnowlong](../dynamics-nav/includes/navnowlong_md.md)] by using the following features.  
  
|Feature|Description|See|  
|-------------|-----------------|---------|  
|Component Object Model \(COM\) technologies|You can extend the functionality by implementing automation and custom controls. The [!INCLUDE[nav_windows](../dynamics-nav/includes/nav_windows_md.md)] supports automation servers by acting as an automation controller and using OCXs \(custom controls\).<br /><br /> **NOTE:** COM is not supported by the [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)].|[Extending Microsoft Dynamics NAV Using COM](../dynamics-nav/Extending-Microsoft-Dynamics-NAV-Using-COM.md)|  
|Microsoft .NET Framework interoperability|You can extend the [!INCLUDE[rtc](../dynamics-nav/includes/rtc_md.md)]s and [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] with functionality that is available in Microsoft .NET Framework assemblies. You can take advantage of .NET Framework interoperability so that [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] objects can interact with the .NET Framework objects.|[Extending Microsoft Dynamics NAV Using Microsoft .NET Framework Interoperability](../dynamics-nav/Extending-Microsoft-Dynamics-NAV-Using-Microsoft-.NET-Framework-Interoperability.md)|  
|Control add\-ins|A control add\-in is a custom control, or visual element, for displaying and modifying data on pages in the [!INCLUDE[nav_windows](../dynamics-nav/includes/nav_windows_md.md)]. Control add\-ins are delivered as Microsoft .NET Framework–based assemblies. [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] includes the client extensibility API for creating your own control add\-ins.|[Extending the Windows Client Using Control Add\-ins](../dynamics-nav/Extending-the-Windows-Client-Using-Control-Add-ins.md)|  
|NAV Apps|NAV Apps are a new way to extend and customize a [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] deployment without the need to directly modify source objects.|[Extending Microsoft Dynamics NAV Using Extension Packages](../dynamics-nav/Extending-Microsoft-Dynamics-NAV-Using-Extension-Packages.md)|  
  
> [!NOTE]  
>  When [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] data is consumed in a browser or by a Microsoft .NET Framework assembly, users cannot be authenticated if their user name or password contains Unicode characters. This is a limitation in the basic authentication mechanism that is defined in the HTTP\/1.1 specification.  
>   
>  The same limitation applies to exposing [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] data in web services.  
  
## See Also  
 [Extending Microsoft Dynamics NAV Using COM](../dynamics-nav/Extending-Microsoft-Dynamics-NAV-Using-COM.md)   
 [Extending Microsoft Dynamics NAV Using Microsoft .NET Framework Interoperability](../dynamics-nav/Extending-Microsoft-Dynamics-NAV-Using-Microsoft-.NET-Framework-Interoperability.md)   
 [Extending the Windows Client Using Control Add\-ins](../dynamics-nav/Extending-the-Windows-Client-Using-Control-Add-ins.md)   
 [Extending Microsoft Dynamics NAV Using Extension Packages](../dynamics-nav/Extending-Microsoft-Dynamics-NAV-Using-Extension-Packages.md)