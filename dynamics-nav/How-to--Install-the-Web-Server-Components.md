---
title: "How to: Install the Web Server Components"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: 79e434bd-a66e-4846-b102-97c41b0646b3
caps.latest.revision: 36
manager: edupont
---
# How to: Install the Web Server Components
To deploy the [!INCLUDE[nav_web](includes/nav_web_md.md)] and [!INCLUDE[nav_tablet](includes/nav_tablet_md.md)], you install the [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)] on a computer that is running Internet Information Services \(IIS\). To access the [!INCLUDE[nav_web](includes/nav_web_md.md)], you must have a web browser and a network connection to a [!INCLUDE[nav_server](includes/nav_server_md.md)] instance that connects to a [!INCLUDE[navnow](includes/navnow_md.md)] database. The following illustration shows the components involved in the setup.  

 ![Install NAV Web client on same computer as server](media/NAV_WebClient_Installation_OneComputer.png "NAV\_WebClient\_Installation\_OneComputer")  

 You can install [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)] on the same computer as the [!INCLUDE[nav_server](includes/nav_server_md.md)] or on a separate computer.  

> [!NOTE]  
>  You do not need a [!INCLUDE[nav_server](includes/nav_server_md.md)] instance or SQL Server database to install the [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)]. You can install these components separately and then later configure the [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)] to use them.  

### Prerequisites  

-   [!INCLUDE[navnowlong](includes/navnowlong_md.md)] installation media. For example, this could be a DVD or network drive that contains the [!INCLUDE[navnowlong](includes/navnowlong_md.md)] installation files.  

-   Verify that the system requirements are met on the computer that you want to install [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)]. For more information, see [System Requirements for Microsoft Dynamics NAV](System-Requirements-for-Microsoft-Dynamics-NAV.md).  

-   Install Internet Information Services 7.0 at a minimum.  

     Make sure that the required features are enabled. For more information, see [How to: Install and Configure Internet Information Services for Microsoft Dynamics NAV Web Client](How-to--Install-and-Configure-Internet-Information-Services-for-Microsoft-Dynamics-NAV-Web-Client.md)  

     Instead of installing and configuring IIS manually, you can use [!INCLUDE[navnow](includes/navnow_md.md)] Setup to install IIS and enable the required features. If IIS is already installed, then Setup will enable any required features that are not currently enabled.  

-   If you want to configure SSL on the connection to [!INCLUDE[nav_web](includes/nav_web_md.md)], then complete the following procedures:  

    -   Obtain an SSL certificate.  

    -   Import the certificate into the local computer store of the computer on which you will install the [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)].  

    -   Obtain the certificate's thumbprint.  

     For more information about these procedures, see [Walkthrough: Configuring Web Services to Use SSL \(SOAP and OData\)](Walkthrough:-Configuring-Web-Services-to-Use-SSL-\(SOAP-and-OData\).md).  

    > [!NOTE]  
    >  If you do not want to configure SSL when you install the [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)], you can configure it after installation. For more information, see [How to: Configure SSL to Secure the Connection to Microsoft Dynamics NAV Web Client](How-to--Configure-SSL-to-Secure-the-Connection-to-Microsoft-Dynamics-NAV-Web-Client.md).  

## Installing the Microsoft Dynamics NAV Web Server  
 To install the [!INCLUDE[nav_web](includes/nav_web_md.md)], you run [!INCLUDE[navnow](includes/navnow_md.md)] Setup on a computer that is running IIS, and then choose the [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)] option.  

#### To install [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)] using the [!INCLUDE[navnow](includes/navnow_md.md)] Setup Wizard  

1.  On the computer that is running IIS, open the [!INCLUDE[navnowlong](includes/navnowlong_md.md)] installation media.  

2.  Double-click the setup.exe file to start the [!INCLUDE[navnow](includes/navnow_md.md)] Setup Wizard.  

     If you have already installed one or more [!INCLUDE[navnow](includes/navnow_md.md)] components on the computer, you will see the **Maintenance** page instead of the **Welcome** page. In this case, choose **Add or remove components**, and then go to step 7.  

3.  Choose the **Next** button.  

4.  To accept the license terms, choose **I accept**.  

5.  On the **Microsoft Dynamics NAV Setup** page, choose **Choose an installation option**.  

6.  On the **Choose an Installation Option** page, choose **Custom**.  

7.  On the **Customize the Installation** page, select the **NAV Web Server Components** check box, and then choose **Run from My Computer**.  

8.  Choose the **Next** button to go to the **Specify Parameters** page.  

9. In the **Server** section, set the following parameters to configure the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance.  

    |Parameter|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
    |---------------|---------------------------------------|  
    |**Server Name**|Specifies the name of the computer that is running [!INCLUDE[nav_server](includes/nav_server_md.md)] for this client.|  
    |**Client Services Port**|The listening TCP port for the computer that is running [!INCLUDE[nav_server](includes/nav_server_md.md)].|  
    |**Service Name**|The name of the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance to connect to.|  

    > [!NOTE]  
    >  If you currently do not know the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance or you want set up the [!INCLUDE[nav_server](includes/nav_server_md.md)] later, then use the default values.  

10. In the **Web Server Components** section, set the **Port** parameter to the TCP port to use for the [!INCLUDE[nav_web](includes/nav_web_md.md)] website.  

11. If you want to add an item on the **Start** menu for opening the [!INCLUDE[nav_web](includes/nav_web_md.md)], set the **Add link to Start menu** parameter to **Yes**.  

12. Set the **Install IIS prerequisites** parameter to one of the following values.  

    |Value|Description|  
    |-----------|-----------------|  
    |**Install**|Setup enables IIS and the required features for the [!INCLUDE[nav_web](includes/nav_web_md.md)] and installs the [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)]. If IIS is already enabled on the computer, then Setup enables any required features that are not currently enabled.|  
    |**Detect**|Setup detects whether IIS and the required features for the [!INCLUDE[nav_web](includes/nav_web_md.md)] are enabled on the computer, and then does the following:<br /><br /> -   If the required IIS features are enabled, then Setup installs the [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)].<br />-   If any IIS features are not enabled, then Setup does not install the [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)] and an error report is generated that lists the required features. You must enable the required features, and then run Setup again to install the [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)].|  
    |**Skip**|Setup installs the [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)] without detecting whether IIS or the required features are enabled. Setup does not change the IIS setup.|  

13. Verify the parameters, and then choose **Apply** to complete the installation.  

14. When Setup is complete, choose the **Close** button.  

 A website called [!INCLUDE[navnowlong](includes/navnowlong_md.md)] Web Client is added on the IIS. The website includes a web application that has the name WebClient. The physical path of the web application is C:\\inetpub\\wwwroot\\DynamicsNav90\\WebClient.  

 The [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)] are also installed in the %systemroot%\\Program Files\\Microsoft Dynamics NAV\\90\\Web Client folder of the computer.  

 For more information about the [!INCLUDE[nav_web](includes/nav_web_md.md)] installation on IIS, see [Deploying the Microsoft Dynamics NAV Web Server Components](Deploying-the-Microsoft-Dynamics-NAV-Web-Server-Components.md).  

#### To open the [!INCLUDE[nav_web](includes/nav_web_md.md)]  

-   To open the [!INCLUDE[nav_web](includes/nav_web_md.md)] from the computer on which you installed the [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)], use one of the following procedures:  

    -   Choose **Start**, in the **Search** box, type **[!INCLUDE[navnowlong](includes/navnowlong_md.md)] Web Client**, and then choose the related link  

    -   Open a web browser, and then in the address box, type **http://localhost:port/DynamicsNAV90/WebClient**. Replace port with the TCP port number that you chose during Setup.  

     For more information, see [How to: Open the Microsoft Dynamics NAV Web Client](How-to--Open-the-Microsoft-Dynamics-NAV-Web-Client.md). If you get an error when trying to open the [!INCLUDE[nav_web](includes/nav_web_md.md)], see [Troubleshooting the Microsoft Dynamics NAV Web Client Installation](Troubleshooting-the-Microsoft-Dynamics-NAV-Web-Client-Installation.md) for information about resolving the problem.  

#### Next Steps  

-   If [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)] was installed on Windows 7, create an inbound rule in the Windows Firewall to allow communication on the TCP port that you chose during Setup.  

     For more information, see [How to: Create an Inbound Rule in Windows Firewall for the Port of Microsoft Dynamics NAV Web Client](How-to--Create-an-Inbound-Rule-in-Windows-Firewall-for-the-Port-of-Microsoft-Dynamics-NAV-Web-Client.md).  

-   If the [!INCLUDE[nav_web](includes/nav_web_md.md)] is installed on a different computer than [!INCLUDE[nav_server](includes/nav_server_md.md)], set up delegation on [!INCLUDE[nav_server](includes/nav_server_md.md)] from the [!INCLUDE[nav_web](includes/nav_web_md.md)].  

     For more information, see [How to: Configure Delegation for Microsoft Dynamics NAV Web Client](How-to--Configure-Delegation-for-Microsoft-Dynamics-NAV-Web-Client.md).  

-   If you want to change the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance that the [!INCLUDE[nav_web](includes/nav_web_md.md)] connects to, then modify the web.config file for the [!INCLUDE[nav_web](includes/nav_web_md.md)] website.  

     For more information, see [How to: Change the Microsoft Dynamics NAV Server for the Microsoft NAV Web Client](How-to--Change-the-Microsoft-Dynamics-NAV-Server-for-the-Microsoft-NAV-Web-Client.md).  

-   If you want to help secure the communication with the [!INCLUDE[nav_web](includes/nav_web_md.md)], configure SSL.  

     For more information, see [How to: Configure SSL to Secure the Connection to Microsoft Dynamics NAV Web Client](How-to--Configure-SSL-to-Secure-the-Connection-to-Microsoft-Dynamics-NAV-Web-Client.md).  

## See Also  
 [Deploying the Microsoft Dynamics NAV Web Server Components](Deploying-the-Microsoft-Dynamics-NAV-Web-Server-Components.md)   
 [Troubleshooting the Microsoft Dynamics NAV Web Client Installation](Troubleshooting-the-Microsoft-Dynamics-NAV-Web-Client-Installation.md)
