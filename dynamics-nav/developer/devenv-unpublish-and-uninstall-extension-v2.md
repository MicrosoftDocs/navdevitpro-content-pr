---
title: "How to Unpublish and Uninstall an Extension v2.0"
description: "Description of the process of upublishing and uinstalling an extension"
author: jswymer
ms.custom: na
ms.date: 15/01/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.author: jswymer
---

## Unpublishing and Uninstalling Extensions
It helps to understand the difference between uninstalling and unpublishing an extension:
 
-   *Uninstalling* an extension is done on the tenant level. It makes an extension unavailable to users in the client, removing any user interface that the extension provides. Business data that has been collected through the use of the extension is not lost; but preserved. So if you reinstall an extension that has not been unpublished, the data is still available. You must uninstall an extension before you can unpublish it.

-   *Unpublishing* an extension is done on the [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance level. This removes the extension from the server instance's app catalog, and deletes the business data collected through the use of the extension. An extension cannot be unpublished if it is installed on a tenant of the server instance.

## Uninstalling extensions
You can uninstall an extension by using the [!INCLUDE[nav_shell_md](includes/nav_shell_md.md)] or from the client. 

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

## Unpublishing extensions
Like publishing an extensions, you unpublish an extension on a [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance by using the [!INCLUDE[nav_shell_md](includes/nav_shell_md.md)].

### Get an overview of published extension
A server instance can have several published extensions, and unpublishing the extensions requires that you provide information about the extension, like the name, version or path to extension package file. To get this information, you can run the the [Get-NAVAppInfo cmdlet](https://docs.microsoft.com/en-us/powershell/module/microsoft.dynamics.nav.apps.management/get-navappinfo) on the server instance:

```
Get-NAVAppInfo -ServerInstance YourDynamicsNAVServer
```

### Unpublish an extension
To unpublish the extension, run the [Unpublish-NAVApp cmdlet](https://go.microsoft.com/fwlink/?linkid=616080). You can unpublish the extension by specifying the path to extension package file or by the extension name. The following examples unpublishes an extension by using its extension package file path `.\MyExtension.app`. 

```  
Unpublish-NAVApp -ServerInstance YourDynamicsNAVServer -Path '.\MyExtension.app'  
``` 
The following example unpublishes an extension by using its name `My Extension` and version `1.0.0.0`:

```  
Unpublish-NAVApp -ServerInstance YourDynamicsNAVServer -Name "My Extension" -Version 1.0.0.0
```  

The following example combines the Get-NAVAppInfo and Unpublish-NAVApp cmldets into a single command:

```  
Get-NAVAppInfo -ServerInstance YourDynamicsNAVServer -Name 'My Extension' -Version 1.0.0.0 | Unpublish-NAVApp
```  




## See Also  
[Developing Extensions](devenv-dev-overview.md)