---
title: "How to: Install and Configure Internet Information Services for Microsoft Dynamics NAV Web Client"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 890e4a5b-2f43-4cb8-bc7a-18261eaf8139
caps.latest.revision: 19
manager: terryaus
---
# How to: Install and Configure Internet Information Services for Microsoft Dynamics NAV Web Client
This topic describes how to install and configure Internet Information Service \(IIS\) for the [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)]. To deploy the [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)], you install the [!INCLUDE[nav_web_server](../dynamics-nav/includes/nav_web_server_md.md)] on a computer that running IIS 7.0 or IIS 8.0. A website for [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)] is installed on the IIS.  
  
 IIS must have the following features enabled:  
  
-   .NET Extensibility \(on Windows 7 and Windows Server 2008\), .NET Extensibility 4.5 \(on Windows 8 and Windows Server 2012\), .NET Extensibility 4.6 \(on Windows 10\)  
  
-   ASP.NET \(on Windows 7 and Windows Server 2008\), ASP.NET 4.5 \(on Windows 8 and Windows Server 2012\), or ASP.NET 4.6 \(on Windows 10\)  
  
-   ISAPI Extensions  
  
-   ISAPI Filters  
  
-   Request Filtering  
  
-   Windows Authentication  
  
-   Static Content  
  
-   HTTP Activation  
  
 The procedure is slightly different for the different versions of Windows. For more information, see the following sections:  
  
-   [Installing IIS Features on Windows 7](../Topic/How%20to:%20Install%20and%20Configure%20Internet%20Information%20Services%20for%20Microsoft%20Dynamics%20NAV%20Web%20Client.md#Win7)  
  
-   [Installing IIS Features on Windows Server 2008 and Windows Server 2008 R2](../Topic/How%20to:%20Install%20and%20Configure%20Internet%20Information%20Services%20for%20Microsoft%20Dynamics%20NAV%20Web%20Client.md#ws2008)  
  
-   [Installing IIS Features on Windows 8 and Windows 10](../Topic/How%20to:%20Install%20and%20Configure%20Internet%20Information%20Services%20for%20Microsoft%20Dynamics%20NAV%20Web%20Client.md#Win8)  
  
-   [Installing IIS Features on Windows Server 2012](../Topic/How%20to:%20Install%20and%20Configure%20Internet%20Information%20Services%20for%20Microsoft%20Dynamics%20NAV%20Web%20Client.md#WS2012)  
  
> [!NOTE]  
>  Instead of manually installing IIS, you can use the [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] Setup wizard to install and enable the IIS features. For more information, see [Using Microsoft Dynamics NAV Setup to Install IIS Features](../dynamics-nav/Using-Microsoft-Dynamics-NAV-Setup-to-Install-IIS-Features.md).  
  
##  <a name="Win7"></a> Installing IIS Features on Windows 7  
 The following procedure describes how to install IIS and the required features for the [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)], including HTTP activation, on Windows 7.  
  
#### To install IIS features on Windows 7  
  
1.  On the **Start** menu, choose **Control Panel**, and then choose **Programs**.  
  
2.  Under **Programs and Features**, choose **Turn Windows features on or off.**  
  
3.  In the **Windows features** list, expand **Internet Information Services**, and then expand **World Wide Web Services**.  
  
4.  Expand **Application Development Features**, and select the following features:  
  
    -   **.NET Extensibility**  
  
    -   **ASP.NET**  
  
    -   **ISAPI Extensions**  
  
    -   **ISAPI Filters**  
  
5.  Expand **Security**, and then select the following features:  
  
    -   **Request Filtering**  
  
    -   **Windows Authentication**  
  
6.  Expand **Common HTTP Features**, and then select the **Static Content** feature.  
  
7.  To install Internet Information Service \(IIS\) Manager, under **Internet Information Services**, expand **Web Management Tools**, and then select **IIS Management Console**.  
  
     This step is optional. You use Internet Information Service IIS Manager to manage local and remote web servers and sites.  
  
8.  Choose the **OK** button to complete the installation.  
  
9. In the **Windows features** list, expand **Microsoft .NET Framework**, and then select **Windows Communication Foundation HTTP Activation**.  
  
10. To verify that the web server has been installed correctly, start your browser, and then type **http:\/\/localhost** in the address.  
  
     The default web site opens and should display an IIS 7 image. If the IIS 7 image does not appear, then verify that you have configured static content on IIS, as described in step 6.  
  
    > [!NOTE]  
    >  To open Internet Information Services \(IIS\) Manager, on the **Start** menu, in the **Search Programs and Files** box, type **inetmgr**, and then press Enter.  
  
##  <a name="ws2008"></a> Installing IIS Features on Windows Server 2008 and Windows Server 2008 R2  
 The following procedure describes how to install IIS and the required features for the [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)] on Windows Server 2008 and Windows Server 2008 R2.  
  
#### To install IIS features on Windows Server 2008 and Windows Server 2008 R2  
  
1.  On the **Start** menu, choose **All Programs**, choose **Administrative Tools**, and then choose **Server Manager**.  
  
2.  In the navigation pane, choose **Roles**, and then choose **Add Roles**.  
  
3.  In the **Before You Begin** window, choose the **Next** button.  
  
4.  In the **Select Server Roles** window, select **Web Server \(IIS\)**, and then choose **Next**, and then choose **Next** again.  
  
5.  In the **Select Role Service** window, expand **Common HTTP Features**, and then select **Static Content**. Other features that are selected by default can remain selected.  
  
6.  Expand **Application Development Features**, and select the following features:  
  
    -   **ASP.NET**  
  
        > [!NOTE]  
        >  If a message displays asking to add role services for ASP.NET, choose **Add Required Role Services**.  
  
    -   **.NET Extensibility**  
  
    -   **ISAPI Extensions**  
  
    -   **ISAPI Filters**  
  
    > [!NOTE]  
    >  If a message displays asking you to confirm ASP.NET, choose **Allow** to continue.  
  
7.  Expand **Security**, and then select the following features:  
  
    -   **Windows Authentication**  
  
    -   **Request Filtering**  
  
8.  Expand **Management Tools**, and then choose **IIS Management Console**.  
  
     This step is optional. You use Internet Information Service IIS Manager to manage local and remote web servers and sites.  
  
9. Choose **Next**, confirm your selections, and then choose **Install** to complete the installation.  
  
10. When the installation is complete, choose the **Close** button.  
  
11. To verify that the web server has been installed correctly, start your browser, and then type **http:\/\/localhost** in the address.  
  
     The default website opens and should display an IIS 7 image. If the IIS 7 image does not appear, then verify that you have configured static content on IIS, as described in step 5.  
  
    > [!NOTE]  
    >  Internet Information Services Manager was also installed. To verify the installation, on the **Start** menu, choose **Administrative Tools**, and then choose **Internet Information Service \(IIS\) Manager**.  
  
#### To enable HTTP Activation  
  
1.  In the **Server Manager** window, in the navigation pane, choose **Features**, and then choose **Add Features**.  
  
2.  In the **Select Features** window, expand **.NET Framework 3.5 Features**, and then expand **WCF Activation**.  
  
3.  Select **HTTP Activation** window, expand **Common HTTP Features**, and then select **Static Content**. Other features that are selected by default can remain selected.  
  
     If a dialog box appears that prompts you to add features required for HTTP activation, then choose **Add Required Features**.  
  
4.  Choose **Next**, confirm your selections, and then choose **Install** to complete the installation.  
  
5.  When the installation is complete, choose the **Close** button.  
  
##  <a name="Win8"></a> Installing IIS Features on Windows 8 and Windows 10  
 The following procedure describes how to install IIS and the required features for the [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)] on Windows 8 and Windows 10.  
  
#### To install IIS features on Windows 8 and Windows 10  
  
1.  On the **Start** page, choose **Control Panel**, and then choose **Programs**.  
  
2.  Under **Programs and Features**, choose **Turn Windows features on or off.**  
  
     The **Windows features** dialog box appears.  
  
3.  Expand the root\-level item **.NET Framework 4.5 Advanced Services** \(for Windows 8\) or **.NET Framework 4.6 Advanced Services** \(for Windows 10\), and then do the following:  
  
    -   Select **ASP.NET 4.5** \(for Windows 8\) or **ASP.NET 4.6** \(for Windows 10\).  
  
    -   Expand **WCF Services**, and then select **HTTP Activation**.  
  
4.  Expand the root\-level item **Microsoft .NET Framework 3.5 \(including .NET 2.0 and 3.0\)**, and then select **Windows Communication Foundation HTTP Activation**.  
  
    > [!NOTE]  
    >  The **Microsoft .NET Framework 3.5 \(including .NET 2.0 and 3.0\)** item is only available if.NET Framework 3.50 is installed. If the item is not shown, then there is no action for this step.  
  
5.  Expand the root\-level item **Internet Information Services**, expand **World Wide Web Services**, and then do the following:  
  
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
  
8.  To verify that the web server has been installed correctly, start your browser, and then type **http:\/\/localhost** in the address.  
  
     The default web site opens and should display an IIS 8 image.  
  
##  <a name="WS2012"></a> Installing IIS Features on Windows Server 2012  
 The following procedure describes how to install IIS and the required features for the [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)] on Windows Server 2012.  
  
#### To install IIS features on Windows Server 2012  
  
1.  On the **Start** page, choose **Server Manager**.  
  
2.  In the navigation pane, choose **Dashboard**, and then choose **Add roles and features**.  
  
3.  In the **Add Roles and Features Wizard**, in the **Before You Begin** page, choose the **Next** button.  
  
4.  On the **Select installation type** page, select **Role\-based or feature\-based installation**, and then choose the **Next** button.  
  
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
  
18. To verify that the web server has been installed correctly, start your browser, and then type **http:\/\/localhost** in the address.  
  
     The default website opens and should display an IIS 8 image.  
  
## See Also  
 [Deploying the Microsoft Dynamics NAV Web Server Components](../dynamics-nav/Deploying-the-Microsoft-Dynamics-NAV-Web-Server-Components.md)   
 [How to: Install the Web Server Components](../Topic/How%20to:%20Install%20the%20Web%20Server%20Components.md)