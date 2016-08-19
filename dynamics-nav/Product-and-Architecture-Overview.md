---
title: "Product and Architecture Overview"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 275aad2c-ea2c-4291-8381-82b0b92dc1a0
caps.latest.revision: 29
manager: terryaus
---
# Product and Architecture Overview
The [!INCLUDE[navnowlong](../dynamics-nav/includes/navnowlong_md.md)] architecture comprises three core components as well as various additional tools and components. Use [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] Setup to install all components.  
  
## The [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] Three\-Tier Architecture  
 For every deployment of [!INCLUDE[navnowlong](../dynamics-nav/includes/navnowlong_md.md)] you must install the core components, which are the three tiers that make up the [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] architecture.  
  
1.  The [!INCLUDE[rtc](../dynamics-nav/includes/rtc_md.md)] is the *client tier*, which includes a [!INCLUDE[nav_windows](../dynamics-nav/includes/nav_windows_md.md)] and a [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)].  
  
     In addition to the [!INCLUDE[rtc](../dynamics-nav/includes/rtc_md.md)], [!INCLUDE[navnowlong](../dynamics-nav/includes/navnowlong_md.md)] also supports additional client types, including web service clients and a NAS services client for programmatic access. For details on the various client types, see [Client Types](../dynamics-nav/Client-Types.md).  
  
2.  [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] is the *middle or server tier*, managing all business logic and communication.  
  
3.  SQL Server, augmented by [!INCLUDE[navnowlong](../dynamics-nav/includes/navnowlong_md.md)] database components, is the *data tier*.  
  
     If you deploy [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] in a multitenant deployment architecture, the data tier consists of an application database and one or more tenant databases.  
  
> [!IMPORTANT]  
>  When you install [!INCLUDE[navnowlong](../dynamics-nav/includes/navnowlong_md.md)], all components must be from the same version and build of [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] for the software to run correctly.  
  
 You can have multiple instances of any of the core components in a production environment. The following diagram shows a simple installation with two [!INCLUDE[nav_windows](../dynamics-nav/includes/nav_windows_md.md)]s and a [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)] connecting to a single [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] computer, which in turn connects to a computer with SQL Server and the [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] database components.  
  
 ![The RoleTailored architecture.](../dynamics-nav/media/NAV_RoleTailoredArchitecture.png "NAV\_RoleTailoredArchitecture")  
  
 Some common configurations are:  
  
-   All three components on the same computer. This is the configuration for a demo install, and is also typical for a development environment, so that a developer can work on [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] applications without worrying about network connections and inter\-component security. See [Walkthrough: Installing the Demo Version](../Topic/Walkthrough:%20Installing%20the%20Demo%20Version.md).  
  
-   [!INCLUDE[rtc](../dynamics-nav/includes/rtc_md.md)] and [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] on the same computer, data tier on a separate computer. This scenario is described in [Walkthrough: Installing the Three Tiers On Two Computers](../Topic/Walkthrough:%20Installing%20the%20Three%20Tiers%20On%20Two%20Computers.md).  
  
-   Each of the three tiers on a separate computer. This scenario is described in [Walkthrough: Installing the Three Tiers on Three Computers](../Topic/Walkthrough:%20Installing%20the%20Three%20Tiers%20on%20Three%20Computers.md).  
  
## Additional Components  
 In addition to the three core components, there are additional components that enhance or supplement the core components.  
  
|Component|Purpose|  
|---------------|-------------|  
|[Microsoft Dynamics NAV Help Server](../dynamics-nav/Microsoft-Dynamics-NAV-Help-Server.md)|A website with the Help content for [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] in the languages that your version of [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] includes. You can deploy a single Help Server for all users, or customer\-specific Help Servers, depending on your requirements.|  
|Web Server Components. See [How to: Install the Web Server Components](../Topic/How%20to:%20Install%20the%20Web%20Server%20Components.md).|The components that are needed to enable [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)]s to connect with a browser.|  
|[Microsoft Dynamics NAV Server Administration Tool](../dynamics-nav/Microsoft-Dynamics-NAV-Server-Administration-Tool.md)|A tool for configuring and managing [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] and [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] sites.|  
|[Development Environment \(C\-SIDE\)](../dynamics-nav/Development-Environment--C-SIDE-.md)|The Development Environment for creating and modifying [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] applications in C\/AL.|  
|[Microsoft Office Outlook Add\-In](../dynamics-nav/Microsoft-Office-Outlook-Add-In.md)|A component for synchronizing data, such as to\-dos, contacts, and tasks, between [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] and Outlook.|  
|[Automated Data Capture System](../dynamics-nav/Automated-Data-Capture-System.md)|A [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] tool for accurately capturing data for inbound, outbound, and internal documents, primarily in connection with warehouse activities. With ADCS, company employees use handheld devices and radio frequency technology to continuously validate warehouse inventories.|  
|ClickOnce Installer Tools. See [Deploying Microsoft Dynamics NAV Using ClickOnce](../dynamics-nav/Deploying-Microsoft-Dynamics-NAV-Using-ClickOnce.md).|A set of tools designed to create ClickOnce deployments for applications for the [!INCLUDE[nav_windows](../dynamics-nav/includes/nav_windows_md.md)].|  
  
## See Also  
 [Deployment](../dynamics-nav/Deployment.md)   
 [Working with Microsoft Dynamics NAV Setup](../dynamics-nav/Working-with-Microsoft-Dynamics-NAV-Setup.md)   
 [Multitenant Deployment Architecture](../dynamics-nav/Multitenant-Deployment-Architecture.md)