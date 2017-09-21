---
title: "How to: Set Up Multiple Web Server Instances for the Microsoft Dynamics NAV Web Client"
ms.custom: na
ms.date: 21/09/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
author: jswymer
---
# Creating and Managing Dynamics NAV Web Server Instances by using PowerShell
You can use the [!INCLUDE[navnow](includes/navnow_md.md)] Setup wizard to install the [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)] and create a single web server instance in IIS for the [!INCLUDE[nav_web](includes/nav_web_md.md)]. But there may be scenarios when you want to set up multiple [!INCLUDE[nav_web](includes/nav_web_md.md)] instances. For example, you could set up a separate [!INCLUDE[nav_web](includes/nav_web_md.md)] instance for the different companies of a business. For this scenario, you can use the [!INCLUDE[nav_shell_md](includes/nav_shell_md.md)], which contains the following cmdlets that enable you to manage  [!INCLUDE[nav_web_server_instance_md](includes/nav_web_server_instance_md.md)] instances.

|Cmdlet|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|
|------------|---------------------------------------|
|[New-NAVWebServerInstance](Microsoft.Dynamics.NAV.Management/New-NAVWebServerInstance.md)|Creates a new [!INCLUDE[nav_web_server_instance_md](includes/nav_web_server_instance_md.md)] instance and binds this instance to a Dynamics NAV Server instance. |
|[Set-NAVWebServerInstanceConfiguration](Microsoft.Dynamics.NAV.Management/Set-NAVWebServerInstanceConfiguration.md)|Specifies configuration values for a named [!INCLUDE[nav_web_server_instance_md](includes/nav_web_server_instance_md.md)] instance.|
|[Get-NAVWebServerInstance](Microsoft.Dynamics.NAV.Management/Get-NAVWebServerInstance.md)|Gets the information about the [!INCLUDE[nav_web_server_instance_md](includes/nav_web_server_instance_md.md)] instances that are registered on a computer.|
|[Remove-NAVWebServerInstance](Microsoft.Dynamics.NAV.Management/Remove-NAVWebServerInstance.md)| Removes an existing [!INCLUDE[nav_web_server_instance_md](includes/nav_web_server_instance_md.md)] instance.|  

## Create a [!INCLUDE[nav_web_server_instance_md](includes/nav_web_server_instance_md.md)] instance
1.  On the computer that is running IIS, run [!INCLUDE[nav_shell_md](includes/nav_shell_md.md)] as an Administrator.  
  
     On the **Start** menu, right-click **[!INCLUDE[navnow](includes/navnow_md.md)] Administration Shell**, and then choose **Run as Administrator**.  
  
2.  At the command prompt, type one of the the following commands, depending on whether you want to create a RootSite or SubSite deployment type (see [Site Deployment Types](How-to--Set-Up-Multiple-Web-Server-Instances-for-the-Microsoft-Dynamics-NAV-Web-Client.md#WebClientonIIS):  
  
    ```  
    New-NAVWebServerInstance -WebServerInstance MyWebApp -Server NAVServer -ServerInstance NAVServerInstance -SiteDeploymentType RootSite
    ```  

    ```  
    New-NAVWebServerInstance -WebServerInstance MyWebApp -Server NAVServer -ServerInstance NAVServerInstance -SiteDeploymentType Subsite -ContainerName MySiteContainer
    ```  
  
    -   Susbtitute *MyWebApp* to the name that you want to give the web application in IIS for the web server instance. If you are creating a SubSite deployment type, this name will become part of the URL for opening the [!INCLUDE[nav_web](includes/nav_web_md.md)] application, for example, http://MyWebServer:8080/MyNavWebApp.  
  
    -   Susbtitute *NAVServer* to the name of the computer that is running the [!INCLUDE[nav_server](includes/nav_server_md.md)] to which you want to connect.  
  
    -   Susbtitute *NAVServerInstance* to the name of the instance on the [!INCLUDE[nav_server](includes/nav_server_md.md)]. 

    > [!NOTE]  
    >  This command only sets the required parameters of the NAVWebServerInstance cmdlet. The cmdlet has several other parameters that can use to configure the web server instance. For more information about the syntax and parameters, see New-NAVWebServerInstance.  
  
4.  Press Enter to run the cmdlet.  
  
     A new web server instance is added.  
  
If you want to change the configuration of the new [!INCLUDE[nav_web_server_instance_md](includes/nav_web_server_instance_md.md)] instance, you can use the Set-NAVWebServerInstanceConfiguration cmdlet or you can modify the configuration file (navsettings.json) of the instance directly. For more information, see [Configuring Microsoft Dynamics NAV Web Client by Modifying the Web.config File](Configuring-Microsoft-Dynamics-NAV-Web-Client-by-Modifying-the-Web.config-File.md).  

## <a name="WebClientonIIS"></a>Site Deployment Types
There are two types of [!INCLUDE[nav_web_server_instance_md](includes/nav_web_server_instance_md.md)] instances that you can create: RootSite or SubSite. The instance types have a different hierarchical structure in IIS, which influences the configuration and the URLs for the accessing the [!INCLUDE[nav_web](includes/nav_web_md.md)
 
### RootSite
A *RootSite* instance is a root-level web site that is complete with content files for serving the [!INCLUDE[nav_web](includes/nav_web_md.md)]. , and it configured with its own set of bindings for accessing the site, such as protocol (http or https) and communication port. The URL for the web server instance has the format:

`http://[WebserverComputerName]:[port]`

For example: `http://localhost:8080` or `https://localhost:8080`. 

## SubSite
A *SubSite* instance is an web application that is under a container web site. The container web site is configured with a set of bindings, but the site itself has no content files. The content files are contained in the application (subsite). The application inherits the bindings and other configuration settings from the container web site. The URL of a subsite instance is generally longer than a rootsite because it also contains the application's alias (or virtual path), which you define. The URL for a subsite instance has the format:

`http://[WebserverComputerName]:[port]/[WebServerInstance]`

For example: `http://localhost:8080/dynamicsnav` or `https://localhost:8080/dynamicsnav`. 
  
## See Also  
 [Deploying the Microsoft Dynamics NAV Web Server Components](Deploying-the-Microsoft-Dynamics-NAV-Web-Server-Components.md)   
 [How to: Install the Web Server Components](How-to--Install-the-Web-Server-Components.md)   
 [Configuring Microsoft Dynamics NAV Web Client by Modifying the Web.config File](Configuring-Microsoft-Dynamics-NAV-Web-Client-by-Modifying-the-Web.config-File.md)