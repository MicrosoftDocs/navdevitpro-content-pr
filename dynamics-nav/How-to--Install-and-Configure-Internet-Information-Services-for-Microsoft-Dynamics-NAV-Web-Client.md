---
title: "How to: Install and Configure Internet Information Services for Microsoft Dynamics NAV Web Client"
ms.custom: na
ms.date: 02/08/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 890e4a5b-2f43-4cb8-bc7a-18261eaf8139
caps.latest.revision: 19
author: jswymer
---
# How to: Install and Configure Internet Information Services for Microsoft Dynamics NAV Web Client
This topic describes how to install and configure Internet Information Service \(IIS\) for the [!INCLUDE[nav_web](includes/nav_web_md.md)]. To deploy the [!INCLUDE[nav_web](includes/nav_web_md.md)], you install the [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)] on a computer that running IIS 7.5, IIS 8.0, IIS 8.0, or IIS 10.0. A website for [!INCLUDE[nav_web](includes/nav_web_md.md)] is installed on the IIS.  
  
 IIS must have the following features enabled:  
  
-   NET Extensibility 4.5 \(on Windows 8, Windows 8.1, and Windows Server 2012\), .NET Extensibility 4.6 \(on Windows 10\)  
  
-   ASP.NET 4.5 \(on Windows 8, Windows 8.1, and Windows Server 2012\), or ASP.NET 4.6 \(on Windows 10\)  
  
-   ISAPI Extensions  
  
-   ISAPI Filters  
  
-   Request Filtering  
  
-   Windows Authentication  
  
-   Static Content  
  
-   HTTP Activation  
  
 The procedure is slightly different for the different versions of Windows. For more information, see the following sections:  
  
-   [Installing IIS Features on Windows 8 and Windows 10](How-to--Install-and-Configure-Internet-Information-Services-for-Microsoft-Dynamics-NAV-Web-Client.md#Win8)  
  
-   [Installing IIS Features on Windows Server 2012](How-to--Install-and-Configure-Internet-Information-Services-for-Microsoft-Dynamics-NAV-Web-Client.md#WS2012)  
  
> [!NOTE]  
>  Instead of manually installing IIS, you can use the [!INCLUDE[navnow](includes/navnow_md.md)] Setup wizard to install and enable the IIS features. For more information, see [Using Microsoft Dynamics NAV Setup to Install IIS Features](Using-Microsoft-Dynamics-NAV-Setup-to-Install-IIS-Features.md).  
  
#### To install IIS features on Windows 8, Windows 8.1, and Windows 10  
  
1.  On the **Start** page, choose **Control Panel**, and then choose **Programs**.  
  
2.  Under **Programs and Features**, choose **Turn Windows features on or off.**  
  
     The **Windows features** dialog box appears.  
  
3.  Expand the root-level item **.NET Framework 4.5 Advanced Services** \(for Windows 8\) or **.NET Framework 4.6 Advanced Services** \(for Windows 10\), and then do the following:  
  
    -   Select **ASP.NET 4.5** \(for Windows 8\) or **ASP.NET 4.6** \(for Windows 10\).  
  
    -   Expand **WCF Services**, and then select **HTTP Activation**.  
  
4.  Expand the root-level item **Microsoft .NET Framework 3.5 \(including .NET 2.0 and 3.0\)**, and then select **Windows Communication Foundation HTTP Activation**.  
  
    > [!NOTE]  
    >  The **Microsoft .NET Framework 3.5 \(including .NET 2.0 and 3.0\)** item is only available if.NET Framework 3.50 is installed. If the item is not shown, then there is no action for this step.  
  
5.  Expand the root-level item **Internet Information Services**, expand **World Wide Web Services**, and then do the following:  
  
    1.  Expand **Application Development Features**, and select the following features:  
  
        -   **.NET Extensibility 3.5** \(if .NET Framework 3.5 is installed\)  
  
        -   **.NET Extensibility 4.5** \(for Windows 8\) or **.NET Extensibility 4.6** \(for Windows 10\)  
  
        -   **ASP.NET 3.5** \(if .NET Framework 3.5 is installed\)  
  
        -   **ASP.NET 4.5** \(for Windows 8\) or **ASP.NET 4.6** \(for Windows 10\)  
  
        -   **ISAPI Extensions**  
  
        -   **ISAPI Filters**  
  
    2.  Expand **Common HTTP Features**, and then select the **Static Content** feature.  
  
    3.  Expand **Security**, and then select the following features:  
  
        -   **Request Filtering**  
  
        -   **Windows Authentication**  
  
6.  Under **Internet Information Services**, expand **Web Management Tools**, and then select **IIS Management Console**.  
  
     This is an optional step to install Internet Information Service IIS Manager. You use Internet Information Service IIS Manager to manage local and remote web servers and sites.  
  
7.  Choose the **OK** button to complete the installation.  
  
8.  To verify that the web server has been installed correctly, start your browser, and then type **http://localhost** in the address.  
  
     The default web site opens and should display an IIS 8 image.  
  
##  <a name="WS2012"></a> Installing IIS Features on Windows Server 2012  
 The following procedure describes how to install IIS and the required features for the [!INCLUDE[nav_web](includes/nav_web_md.md)] on Windows Server 2012.  
  
#### To install IIS features on Windows Server 2012  
  
1.  On the **Start** page, choose **Server Manager**.  
  
2.  In the navigation pane, choose **Dashboard**, and then choose **Add roles and features**.  
  
3.  In the **Add Roles and Features Wizard**, in the **Before You Begin** page, choose the **Next** button.  
  
4.  On the **Select installation type** page, select **Role-based or feature-based installation**, and then choose the **Next** button.  
  
5.  On the **Select destination server** page, select **Select a server from the server pool**, select your server from **Server Pool** list, and then choose the **Next** button.  
  
6.  In the **Select Server Roles** window, select **Web Server \(IIS\)**, and then choose the **Next** button.  
  
7.  If the **Add features that are required for Web Server \(IIS\)** dialog box appears, then choose **Add Features**.  
  
    > [!NOTE]  
    >  If you do not want to install the IIS Management Console, clear the **Include management tools** check box, and then choose the **Continue** button.  
  
8.  On the **Select features** page, expand **.NET Framework 4.5**, and then select **ASP.NET 4.5**.  
  
9. Expand **WCF Services**, and then select **HTTP Activation**.  
  
10. In the **Add features that are required for ASP.NET 4.5?** dialog box, choose the **Add Features** button.  
  
     The following additional features are added.  
  
    -   ASP.NET 4.5  
  
    -   ISAPI Extensions  
  
    -   ISAPI Filters  
  
    -   .NET Extensibility 4.5  
  
11. If .NET Framework 3.5 is installed, then do the following:  
  
    1.  Expand the **.NET Framework 3.5 Features** node.  
  
    2.  Select **HTTP Activate**.  
  
    3.  If the **Add features that are required for ASP.NET 3.5** dialog box appears, choose the **Add Features** button.  
  
         The following additional features are added.  
  
        -   .NET Framework 3.5 \(including .NET 2.0 and 3.0\)  
  
        -   .NET Extensibility 3.5  
  
12. On the **Select Features** page, choose the **Next** button.  
  
13. On the **Web Server Role \(IIS\)** page, choose the **Next** button.  
  
14. On the **Select role services** page, verify that the following role services are selected at a minimum.  
  
    -   **Common HTTP Features**  
  
        -   **Static Content**  
  
    -   **Security**  
  
        -   **Request Filtering**  
  
        -   **Windows Authentication**  
  
    -   **Application Development**  
  
        -   **.NET Extensibility 3.5** \(if .NET Framework 3.5 is installed\)  
  
        -   **.NET Extensibility 4.5**  
  
        -   **ASP.NET 3.5** \(if .NET Framework 3.5 is installed\)  
  
        -   **ASP.NET 4.5**  
  
        -   **ISAPI Extensions**  
  
        -   **ISAPI Filters**  
  
    -   **Management Tools** \(optional\)  
  
        -   **IIS Management Console** \(optional\)  
  
    > [!NOTE]  
    >  You can leave other role services that are selected by default as selected.  
  
15. Choose the **Next** button  
  
16. On the **Confirm installation selections** page, choose the **Install** button.  
  
17. On the **Installation progress** page, confirm that your installation completed successfully, and then choose the **Close** button.  
  
18. To verify that the web server has been installed correctly, start your browser, and then type **http://localhost** in the address.  
  
     The default website opens and should display an IIS 8 image.  
  
## See Also  
 [Deploying the Microsoft Dynamics NAV Web Server Components](Deploying-the-Microsoft-Dynamics-NAV-Web-Server-Components.md)   
 [How to: Install the Web Server Components](How-to--Install-the-Web-Server-Components.md)