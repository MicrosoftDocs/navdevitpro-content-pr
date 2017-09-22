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
Although you can use the [!INCLUDE[navnow](includes/navnow_md.md)] Setup wizard to install the [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)] and create a single web server instance in IIS for the [!INCLUDE[nav_web](includes/nav_web_md.md)], there may be scenarios when you want to set up multiple [!INCLUDE[nav_web](includes/nav_web_md.md)] instances. For example, you could set up a separate [!INCLUDE[nav_web](includes/nav_web_md.md)] instance for the different companies of a business. For this scenario, you can use the [!INCLUDE[nav_web_server_instance_md](includes/nav_web_server_instance_md.md)] PowerShell cmdlets that are outlines in the following table.

|Cmdlet|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|
|------------|---------------------------------------|
|[New-NAVWebServerInstance](Microsoft.Dynamics.NAV.Management/New-NAVWebServerInstance.md)|Creates a new [!INCLUDE[nav_web_server_instance_md](includes/nav_web_server_instance_md.md)] instance and binds this instance to a Dynamics NAV Server instance. |
|[Set-NAVWebServerInstanceConfiguration](Microsoft.Dynamics.NAV.Management/Set-NAVWebServerInstanceConfiguration.md)|Specifies configuration values for a named [!INCLUDE[nav_web_server_instance_md](includes/nav_web_server_instance_md.md)] instance.|
|[Get-NAVWebServerInstance](Microsoft.Dynamics.NAV.Management/Get-NAVWebServerInstance.md)|Gets the information about the [!INCLUDE[nav_web_server_instance_md](includes/nav_web_server_instance_md.md)] instances that are registered on a computer.|
|[Remove-NAVWebServerInstance](Microsoft.Dynamics.NAV.Management/Remove-NAVWebServerInstance.md)| Removes an existing [!INCLUDE[nav_web_server_instance_md](includes/nav_web_server_instance_md.md)] instance.|  

## Get started with the [!INCLUDE[nav_web_server_instance_md](includes/nav_web_server_instance_md.md)] cmdlets 

The [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)] cmdlets are contained in a PowerShell script module that has the name **NAVWebClientManagement.psm1**. This module is available on the [!INCLUDE[navnow](includes/navnow_md.md)] intallation media (DVD). It is also installed with [!INCLUDE[nav_server_md](includes/nav_server_md.md)], where the default folder is: [!INCLUDE[navnow_install_md](includes/navnow_install_md.md)]\Service.

There are two ways to start using the cmdlets:

- If you are working on the computer where the [!INCLUDE[nav_server_md](includes/nav_server_md.md)] is installed, then you can run the [!INCLUDE[nav_shell_md](includes/nav_shell_md.md)], which automatically includes the **NAVWebClientManagement.psm1** module.

  For more information, see [Starting a [!INCLUDE[nav_shell](includes/nav_shell_md.md)] Session](Microsoft-Dynamics-NAV-Windows-PowerShell-Cmdlets.md#StartAdminShell)

- Start Windows PowerShell, and then use the [Import-Module](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/import-module) cmdlet to import the **NAVWebClientManagement.psm1** file:

  ```
  Import-Module -Name [filepath]
  ```  
  For example:
  ```
  Import-Module -Name "C:\Program Files\Microsoft Dynamics NAV\110\Service\NAVWebClientManagement.psm1"
  ```

    For more information, see [Starting Windows PowerShell](https://docs.microsoft.com/en-us/powershell/scripting/setup/starting-windows-powershell).

## Creating a [!INCLUDE[nav_web_server_instance_md](includes/nav_web_server_instance_md.md)] instance

### Get Access to the WebPublish folder
To create a new web server instance, you need access to a **WebPublish** folder that contains the content files for the [!INCLUDE[nav_web_md](includes/nav_web_md.md)].

-  This folder is available on the [!INCLUDE[navnow](includes/navnow_md.md)] intallation media (DVD) in the path `DVD\WebClient\Microsoft Dynamics NAV\110\Web Client\WebPublish`.

- If you installed the [!INCLUDE[nav_web_server_md](includes/nav_web_server_md.md)], this folder can be found in the folder **[!INCLUDE[navnow_install_md](includes/navnow_install_md.md)]\Web Client**.

You can use either of these locations or you can copy the folder to more convenient location on your computer or network.


### <a name="WebClientonIIS"></a>Decide on the site deployment type for the instance
When you create a new [!INCLUDE[nav_web_server_instance_md](includes/nav_web_server_instance_md.md)] instance, you can choose to create either a RootSite or SubSite type. The instance types have a different hierarchical structure in IIS, which influences the configuration and the URLs for the accessing the [!INCLUDE[nav_web](includes/nav_web_md.md)].
 
**RootSite**

A *RootSite* instance is a root-level web site that is complete with content files for serving the [!INCLUDE[nav_web](includes/nav_web_md.md)]. It is  configured with its own set of bindings for accessing the site, such as protocol (http or https) and communication port.

```
+ DynamicsNAVWebClient (application)
  -en-us
  -en-ca
  -...
  -www
```
The URL for the web server instance has the format:

`http://[WebserverComputerName]:[port]`

For example: `http://localhost:8080` or `https://localhost:8080`. 

**SubSite**

A *SubSite* instance is a web application that is under a container web site. The container web site is configured with a set of bindings, but the site itself has no content files. The content files are contained in the application (subsite). The application inherits the bindings and other configuration settings from the container web site.

```
+ DynamicsNAVWebClient (container web site)
  + Dynamics110-1 (application)
    -en-us
    -en-ca
    -...
    -www
  + Dynamics110-2 (application)
    -en-us
    -en-ca
    -...
    -www    
```

The URL of a subsite instance is generally longer than a rootsite because it also contains the application's alias (or virtual path), which you define. The URL for a subsite instance has the format:

`http://[WebserverComputerName]:[port]/[WebServerInstance]`

For example: `http://localhost:8080/dynamicsnav` or `https://localhost:8080/dynamicsnav`. 

### Run the New-NAVWebServerInstance cmdlet

At the command prompt, run the New-NAVWebServerInstance cmdlet. The following are simple examples for creating a RootSite and SubSite deployment type.

RootSite example:

    ```  
    New-NAVWebServerInstance -WebServerInstance MyWebApp -Server NAVServer -ServerInstance NAVServerInstance -SiteDeploymentType RootSite -WebSitePort 8081 -PublisherFolder "C:\Web Client\WebPublish"
    ```  
SubSite example:

    ```  
    New-NAVWebServerInstance -WebServerInstance MyWebApp -Server NAVServer -ServerInstance NAVServerInstance -SiteDeploymentType Subsite -ContainerName MySiteContainer -Port 8081 -PublisherFolder "C:\WebClient\WebPublish"
    ```  

-  Susbtitute *MyWebApp* to the name that you want to give the web application in IIS for the web server instance. If you are creating a SubSite deployment type, this name will become part of the URL for opening the [!INCLUDE[nav_web](includes/nav_web_md.md)] application, for example, http://MyWebServer:8080/MyNavWebApp.  
  
- Susbtitute *NAVServer* to the name of the computer that is running the [!INCLUDE[nav_server](includes/nav_server_md.md)] to which you want to connect.  
  
-   Susbtitute *NAVServerInstance* with the name of the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance to use.

-  Susbtitute *8081* with the port number that you want to bind the instance to. If you do not specify a port number, then port 80 is used. 
    
-  Substitute *C:\WebClient\WebPublish* with the path to your WebPublish folder. By default, the cmdlet looks in the'[!INCLUDE[navnow_install_md](includes/navnow_install_md.md)]\Web Client' folder. So if you are working on a computer where the [!INCLUDE[nav_web_server_md](includes/nav_web_server_md.md)] are installed, you do not have to set this parameter.

> [!NOTE]  
>  This command only sets the required parameters of the NAVWebServerInstance cmdlet. The cmdlet has several other parameters that can use to configure the web server instance. For more information about the syntax and parameters, see New-NAVWebServerInstance.  
  
After you create the web server intance, if you want to change its configuration, you can use the Set-NAVWebServerInstanceConfiguration cmdlet. Or, you can modify the configuration file (navsettings.json) of the instance directly. For more information, see [Configuring Microsoft Dynamics NAV Web Client by Modifying the Web.config File](Configuring-Microsoft-Dynamics-NAV-Web-Client-by-Modifying-the-Web.config-File.md).  

## See Also  
[Deploying the Microsoft Dynamics NAV Web Server Components](Deploying-the-Microsoft-Dynamics-NAV-Web-Server-Components.md)   
[How to: Install the Web Server Components](How-to--Install-the-Web-Server-Components.md)   
[Configuring Microsoft Dynamics NAV Web Client by Modifying the Web.config File](Configuring-Microsoft-Dynamics-NAV-Web-Client-by-Modifying-the-Web.config-File.md)