---
title: "How to: Publish and Install an Extension v2.0"
description: "Description of the process of publishing and installing an extension"
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 09/04/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.author: solsen
---

# How to: Publish and Install an Extension v2.0
To make your extension available to tenant users requires three basic tasks: publish the extension package to the [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance, synchronize the extension with the tenant database, and install the extension on the tenant.

> [!NOTE]  
>  This article describes how to publish and install the first version of a V2 extension. If you want to publish an install newer version of an extension, see [Upgrading Extensions V2](devenv-upgrading-extensions.md).  

## Publish and synchronize an extension
Publishing an extension to a [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance adds the extension to the app catalog of the server instance, making it available for installation on tenants of the server instance. Publishing updates internal tables, compiles the components of the extension behind-the-scenes, and builds the necessary metadata objects that are used at runtime.

Synchronizing an extension updates the database schema of the tenant database with the database schema that is defined by the extension objects. For example, if a table or table extension is included in the extension, then the respective full or companion table is created in the tenant database.  

### To publish and synchronize an extension

1.  Start the [!INCLUDE[nav_shell_md](includes/nav_shell_md.md)].

2.  To publish the extension, run the [Publish-NAVApp cmdlet](https://go.microsoft.com/fwlink/?linkid=616079).

    The cmdlet takes as parameters the [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance that you want to install to and the .app package file that contains the extension. The following example publishes the extension **MyExtension** to the **YourDynamicsNAVServer** instance.  

    ```  
    Publish-NAVApp -ServerInstance YourDynamicsNAVServer -Path "C:\Users\vmadmin\Desktop\ExtensionName.app"  
    ```  

3.  To synchronize the schema of a tenant database to the extension, run the [Sync-NavApp cmdlet]((https://go.microsoft.com/fwlink/?linkid=846311).

    The following example synchronizes the extension MyExtension: 
   
    ```
    Sync-NavApp -ServerInstance YourDynamicsNAVServer -Name ExtensionName -Path “C:\Users\vmadmin\Desktop\ExtensionName.app”
    ```
The extension can now be installed on tenants.

## Install an extension
After you publish and synchronize an extension, you can install it on tenants to make it available to users. Installing an extension can be done from the [!INCLUDE[navnow_md](includes/navnow_md.md)] client or [!INCLUDE[nav_shell_md](includes/nav_shell_md.md)].

> [!NOTE]  
> Installing an extension will run any installation code that is built-in to the extension. Installation code could, for example, perform operations like populating empty records with data, service callbacks and telemetry, version checks, and messages to users. For more information, see [Writing Extension Install Code](devenv-extension-install-code.md).

### To install an extension by using [!INCLUDE[nav_shell_md](includes/nav_shell_md.md)] 

1. Start the [!INCLUDE[nav_shell_md](includes/nav_shell_md.md)].
2. Use the `Install-NAVApp` cmdlet to install the extension on one or more tenants.

    The following example installs the MyExtension for Tenant1 and Tenant3. In single-tenant deployments, you either specify default as the tenant ID, or you omit the *–Tenant* parameter.  

    ```  
    Install-NAVApp -ServerInstance YourDynamicsNAVServer -Name ”My Extension.app” –Tenant Tenant1, Tenant3  
    ```   

### To install an extension by using the client  

1.  In [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)], use search to open the **Extension Management** page.

    In the **Extension Management** window, you can view the extensions that are published to your server. For each extension, you can see the current installation status. 
2.  Choose an extension to see additional information and to install the extension.  
3.  Review and accept the license agreement.  
4.  Choose the **Install** button to install the extension.

<!--
### To synchronize schemas
Before you install the extension, you must run the `Sync-NavApp` cmdlet. The `Sync-NavApp` synchronizes the schema of a tenant database to a V2 extension before installation; it adds the tables from the extension to the tenant.

    ```
    Sync-NavApp -ServerInstance NAV -Name ExtensionName -Path “C:\Users\vmadmin\Desktop\ExtensionName.app”
    ```

Next, run the `Start-NavAppDataUpgrade` cmdlet to upgrade the data from a previously installed version of an extension to a new version of an extension in the tenant database.

The following example upgrades the app with the specified name and version for the tenant with the ID **Tenant1**.

    ```
    Start-NAVAppDataUpgrade -ServerInstance DynamicsNAV -Name 'Proseware SmartApp' -Version 2.3.4.500 -Tenant 'Tenant1'
    ```

The next example upgrades an app that is returned from the `Get-NAVAppInfo` cmdlet for the tenant with the ID **Tenant1**.

    ```
    Get-NAVAppInfo -ServerInstance DynamicsNAV -Name 'Proseware SmartApp' -Version 2.3.4.500 | Start-NAVAppDataUpgrade -Tenant 'Tenant1'
    ```

This example upgrades the app at the specified path for the tenant with the ID **Tenant1**.

    ```
    Start-NAVAppDataUpgrade -ServerInstance DynamicsNAV -Path '.\Proseware SmartApp.navx' -Tenant 'Tenant1'
    ```
-->


## Unpublishing and uninstalling extensions

*Uninstalling* an extension is done on the tenant level. It makes an extension unavailable to users in the client, removing any user interface that the extension provides. Business data that has been collected through the use of the extension is not lost; but preserved so that if you reinstall the extension, the data is still available.

*Unpublishing* an extension is done on the [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance level. This removes the extension from the server instance's app catalog, and deletes the business data collected through the use of the extension. An extension cannot be unpublished if it is installed on a tenant of the server instance.


### Unpublish extensions

Like publishing an extensions, you unpublish an extension on a [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance by using the [!INCLUDE[nav_shell_md](includes/nav_shell_md.md)].

A server instance can have several published extensions, and unpublishing the extensions requires that you provide information about the extension, like the name, version or path to extension package file. To get this information, you can run the the [Get-NAVAppInfo cmdlet](https://docs.microsoft.com/en-us/powershell/module/microsoft.dynamics.nav.apps.management/get-navappinfo) on the server instance:

```
Get-NAVAppInfo -ServerInstance YourDynamicsNAVServer
```

To unpublish the extension, run the [Unpublish-NAVApp cmdlet](https://go.microsoft.com/fwlink/?linkid=616080). You can unpublish the extension by specifying the path to extension package file or by the extension name. The following examples unpublishes the extension by using its extension package file path `.\MyExtension.app`. 

```  
Unpublish-NAVApp -ServerInstance YourDynamicsNAVServer -Path '.\MyExtension.app'  
``` 
The following example unpublishes the extension by using its name `My Extension`and version `1.0.0.0`:

```  
Unpublish-NAVApp -ServerInstance YourDynamicsNAVServer -Name "My Extension" -Version 1.0.0.0
```  

The following example combines the Get-NAVAppInfo and Unpublish-NAVApp cmldets into a single command:


```  
Get-NAVAppInfo -ServerInstance YourDynamicsNAVServer -Name 'My Extension' -Version 1.0.0.0 | Unpublish-NAVApp
```  

To get a list of the extensions that are installed, run the Get-NAVAppInfo cmdlet (https://docs.microsoft.com/en-us/powershell/module/microsoft.dynamics.nav.apps.management/get-navappinfo) :

    ```
    Get-NAVAppInfo -ServerInstance <ServerInstanceName> -Tenant <TenantID> |ft
    ```
    
    Replace `<ServerInstanceName>` with the name of the [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance that the database connects to. Replace `<TenantID>` with the tenant ID of the database. If you do not have a multitenant server instance, use `default`.

    In the table that appears, V1 extensions are indicated by `CSIDE` in the `Extension Type` column.ing Getting an overview 

1. Start the [!INCLUDE[nav_shell_md](includes/nav_shell_md.md)].



## Uninstall 

To get an overview of the published extensions and their state using the `Get-NAVAppInfo` cmdlet. If no tenants have a specific extension installed, you can completely remove it using the `Unpublish-NAVApp` cmdlet.


Use `Get-NAVAppInfo –Tenant` command to get an overview of the extensions for that tenant, use the `Get-NAVAppTenant` cmdlet to get all tenants that have installed a specified extension, and uninstall an extension using the `Uninstall-NAVApp` cmdlet.

```
UnInstall-NAVApp -ServerInstance YourDynamicsNAVServer -Name ”My Extension.app” –Tenant Tenant1
```  

> [!NOTE]  
>  When you uninstall an extension that includes tables and fields, this impacts the database schema and any data that the tables and fields contain.


## See Also  
[Developing Extensions](devenv-dev-overview.md)