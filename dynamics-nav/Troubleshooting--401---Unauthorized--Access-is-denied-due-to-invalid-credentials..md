---
title: "Troubleshooting: 401 - Unauthorized: Access is denied due to invalid credentials."
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: 797fbf58-eca3-4c86-8644-7a5d3e248641
caps.latest.revision: 10
manager: edupont
---
# Troubleshooting: 401 - Unauthorized: Access is denied due to invalid credentials.
When you try to access the [!INCLUDE[nav_web](includes/nav_web_md.md)], you get the following error:  
  
 **401 - Unauthorized: Access is denied due to invalid credentials. You do not have permission to view this directory or page using the credentials that you supplied.**  
  
## Resolution  
 This error typically occurs when authentication is not configured correctly between the [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)] \([!INCLUDE[nav_web](includes/nav_web_md.md)] site on IIS\) and [!INCLUDE[nav_server](includes/nav_server_md.md)]. To resolve this error, verify that the following conditions are met:  
  
-   The credential type to use for authenticating users is configured correctly in [!INCLUDE[nav_server](includes/nav_server_md.md)] and in the web.config file of the [!INCLUDE[nav_web](includes/nav_web_md.md)] site on IIS.  
  
     For example, if the [!INCLUDE[nav_web](includes/nav_web_md.md)] site is configured for Windows credential type, the [!INCLUDE[nav_server](includes/nav_server_md.md)] must also be configured for Windows credential type.  
  
-   The correct authentication method is enabled on the [!INCLUDE[nav_web](includes/nav_web_md.md)] site on IIS.  
  
    -   For the Windows credential type, enable **Windows authentication**.  
  
    -   For the UserName and NavUserPassword credential types, enable both **Forms authentication** and **Anonymous authentication**.  
  
-   For Windows authentication, the correct authentication providers are configured on the [!INCLUDE[nav_web](includes/nav_web_md.md)] site on IIS.  
  
 For step-by-step instructions about how change or verify these settings, see the [Configuring the Credential Type on the Microsoft Dynamics NAV Web Client Web Site](How-to--Configure%20Authentication%20of%20Microsoft%20Dynamics%20NAV%20Web%20Client%20Users.md#WebClient).  
  
## See Also  
 [Deploying the Microsoft Dynamics NAV Web Server Components](Deploying-the-Microsoft-Dynamics-NAV-Web-Server-Components.md)   
 [Troubleshooting the Microsoft Dynamics NAV Web Client Installation](Troubleshooting-the-Microsoft-Dynamics-NAV-Web-Client-Installation.md)   
 [How to: Install the Web Server Components](How-to--Install%20the%20Web%20Server%20Components.md)