---
title: "Troubleshooting: A fatal error occurred. The connection to SQL server cannot be established"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: b8612c03-8366-4334-94c0-d409f1c4a10b
caps.latest.revision: 8
manager: edupont
---
# Troubleshooting: A fatal error occurred. The connection to SQL server cannot be established
When you try to open [!INCLUDE[nav_web](includes/nav_web_md.md)], you get the following error:  
  
 **A fatal error occurred. The connection to SQL server cannot be established or is no longer usable.**  
  
 There can be various causes of this error. The most common causes are that [!INCLUDE[nav_server](includes/nav_server_md.md)] has stopped or the connection to SQL Server is not configured correctly.  
  
## Resolution  
 This error occurs when [!INCLUDE[nav_server](includes/nav_server_md.md)] cannot connect to SQL Server or to the [!INCLUDE[navnow](includes/navnow_md.md)] database. To resolve this error, verify that the following conditions are met.  
  
-   [!INCLUDE[nav_server](includes/nav_server_md.md)] connects to the correct database by using the correct login account.  
  
     You can do this by using the Microsoft Dynamics NAV Server Administration tool. For more information, see [Microsoft Dynamics NAV Server Administration Tool](Microsoft-Dynamics-NAV-Server-Administration-Tool.md).  
  
-   Login account has the following permissions:  
  
    -   Permission to log on as a service on the computer that is running SQL Server. For more information, see [Provisioning the Microsoft Dynamics NAV Server Account](Provisioning-the-Microsoft-Dynamics-NAV-Server-Account.md).  
  
    -   Set up as a user in the [!INCLUDE[navnow](includes/navnow_md.md)] database on SQL Server with the following role memberships: db\_datareader, db\_datawriter, and db\_ddladmin. For more information, see [Setting Database Owner and Security Administration Permissions](Setting-Database-Owner-and-Security-Administration-Permissions.md)  
  
-   SQL Server has the following configurations:  
  
    -   TCP\/IP protocol is enabled.  
  
    -   SQL Server executable file is allowed through the Windows Firewall.  
  
    -   SQL Server Browser Service is running. This is required only when [!INCLUDE[navnow](includes/navnow_md.md)] used a named database instance, such as NAVDEMO, and [!INCLUDE[nav_server](includes/nav_server_md.md)] is on a different computer than SQL Server. For more information, see [How to: Start SQL Browser Service](How%20to:%20Start%20SQL%20Browser%20Service.md).  
  
     For more information, see [Troubleshooting: SQL Server Connection Problems](Troubleshooting:%20SQL%20Server%20Connection%20Problems.md).  
  
## See Also  
 [Deploying the Microsoft Dynamics NAV Web Server Components](Deploying-the-Microsoft-Dynamics-NAV-Web-Server-Components.md)   
 [Troubleshooting the Microsoft Dynamics NAV Web Client Installation](Troubleshooting-the-Microsoft-Dynamics-NAV-Web-Client-Installation.md)   
 [How to: Install the Web Server Components](How%20to:%20Install%20the%20Web%20Server%20Components.md)   
 [Walkthrough: Installing the Microsoft Dynamics NAV Web Server Components on Three Computers](Walkthrough:%20Installing%20the%20Microsoft%20Dynamics%20NAV%20Web%20Server%20Components%20on%20Three%20Computers.md)