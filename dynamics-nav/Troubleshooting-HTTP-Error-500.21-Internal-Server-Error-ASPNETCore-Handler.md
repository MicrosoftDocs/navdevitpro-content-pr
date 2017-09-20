---
title: "Troubleshooting: HTTP Error 500.21 - Internal Server Error
Handler "aspNetCore" has a bad module "AspNetCoreModule" in its module list"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: b306d263-4c44-4d22-81b8-a3b15070f29a
caps.latest.revision: 14
manager: edupont
---
# Troubleshooting: HTTP Error 500.21 - Internal Server Error Handler "aspNetCore" has a bad module "AspNetCoreModule" in its module list
When you try to access the [!INCLUDE[nav_web](includes/nav_web_md.md)], you get the following error:  
  
 **HTTP Error 500.21 - Internal Server Error Handler "aspNetCore" has a bad module "AspNetCoreModule" in its module list**  

  
## Resolution  
This error can occur if the AspNetCoreModule is not installed properly in IIS on the computer that is running the [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)]. The AspNetCoreModule is installed with Microsoft .NET Core - Windows Server Hosting package or Microsoft .NET Core SDK. You only need one of these programs. You can get this error if neither of these programs has been fully installed or the installation has been damaged. 

To resolve this issue, check the installed programs on the computer, and try the following:

-   If neither Microsoft .NET Core - Windows Server Hosting nor Microsoft .NET Core SDK is not installed, download and install one of the from [Microsoft .NET Core - Windows Server Hosting package](http://go.microsoft.com/fwlink/?LinkId=798480) or [Download .NET Core](https://www.microsoft.com/net/download/core).

-   If either Microsoft .NET Core - Windows Server Hosting or Microsoft .NET Core SDK is installed, repair them. In Control Panel, open **Programs and Features**, select the program, select **Change**, and then select **Repair**.

  
## See Also  
 [Deploying the Microsoft Dynamics NAV Web Server Components](Deploying-the-Microsoft-Dynamics-NAV-Web-Server-Components.md)   
 [Troubleshooting the Microsoft Dynamics NAV Web Client Installation](Troubleshooting-the-Microsoft-Dynamics-NAV-Web-Client-Installation.md)   
 [How to: Install the Web Server Components](How-to--Install-the-Web-Server-Components.md)