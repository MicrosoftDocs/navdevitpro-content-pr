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
ms.prod: "dynamics-nav-2018"
ms.author: jswymer
---

## Unpublishing and Uninstalling Extensions
There are two levels of extension removal: uninstalling and unpublishing:
 
-   *Uninstalling* an extension is done on the tenant level. It makes an extension unavailable to users in the client, removing any user interface that the extension provides. Business data that has been collected through the use of the extension is not lost; but preserved. So if you reinstall an extension that has not been unpublished, the data is still available. You must uninstall an extension before you can unpublish it.

-   *Unpublishing* an extension is done on the [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance level. This removes the extension from the server instance's app catalog, which means that it can no longer be installed on tenants of the server instance. Unpublishing an extension deletes the business data collected through the use of the extension. An extension cannot be unpublished if it is installed on a tenant of the server instance.

## Uninstalling extensions
You can uninstall an extension by using the [!INCLUDE[nav_shell_md](includes/nav_shell_md.md)] or from the client. 

### To install an extension by using [!INCLUDE[nav_shell_md](includes/nav_shell_md.md)] 

1. Start the [!INCLUDE[nav_shell_md](includes/nav_shell_md.md)]. 

    For more information, see [Starting a Microsoft Dynamics NAV Administration Shell Session](Microsoft-Dynamics-NAV-Windows-PowerShell-Cmdlets.md#StartAdminShell). 
2. To get a list of the extensions that are currently installed on a tenant, run the Get-NAVAppInfo cmdlet (https://docs.microsoft.com/en-us/powershell/module/microsoft.dynamics.nav.apps.management/get-navappinfo) with the `Tenant`parameter set. This cmdlet is useful because when uninstall the extension, you will have to provide information about the extensions, such as the its name, version, or path to the extension package file.

    ```
    Get-NAVAppInfo -ServerInstance YourDynamicsNAVServer -Tenant TenantID
    ```

    Replace `TenantID` with the tenant ID of the database. If you do not have a multitenant server instance, use `default` or omit this parameter. 

3. To uninstall an extension, run the [Uninstall-NAVApp cmdlet](https://docs.microsoft.com/en-us/powershell/module/microsoft.dynamics.nav.apps.management/uninstall-navapp].

    The following example uninstalls an extension by using its extension package file path `.\MyExtension.app`. 

    ```  
    Uninstall-NAVApp -ServerInstance YourDynamicsNAVServer -Path '.\MyExtension.app'  
    ``` 

    The following example uninstalls an extension by using its name `My Extension` and version `1.0.0.0`:

    ```  
    Uninstall-NAVApp -ServerInstance YourDynamicsNAVServer -Name "My Extension" -Version 1.0.0.0
    ```  

    The following example combines the Get-NAVAppInfo and Unpublish-NAVApp cmldets into a single command:

    ```  
    Get-NAVAppInfo -ServerInstance YourDynamicsNAVServer -Name 'My Extension' -Version 1.0.0.0 | Uninstall-NAVApp
    ```  

### To uninstall an extension by using the client  

1.  In [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)], use search to open the **Extension Management** page.

    In the **Extension Management** window, you can view the extensions that are installed on the tenant 
2.  Choose an extension, and choose the **Uninstall** action.


## Unpublishing extensions
You unpublish an extension on a [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance by using the [!INCLUDE[nav_shell_md](includes/nav_shell_md.md)].

> [!NOTE]  
>  When you uninstall an extension that includes tables and fields, this impacts the database schema and any data that the tables and fields contain.

1.  Start the [!INCLUDE[nav_shell_md](includes/nav_shell_md.md)]. 

    For more information, see [Starting a Microsoft Dynamics NAV Administration Shell Session](Microsoft-Dynamics-NAV-Windows-PowerShell-Cmdlets.md#StartAdminShell). 

2. To get a list of the extensions that are currently installed on a tenant, run the Get-NAVAppInfo cmdlet (https://docs.microsoft.com/en-us/powershell/module/microsoft.dynamics.nav.apps.management/get-navappinfo) (without the `Tenant`parameter). This is useful because a server instance can have several published extensions, and unpublishing an extension requires that you provide specific information about the extension, like the name, version or path to extension package file. 

    ```
    Get-NAVAppInfo -ServerInstance YourDynamicsNAVServer
    ```

3. To unpublish the extension, run the [Unpublish-NAVApp cmdlet](https://go.microsoft.com/fwlink/?linkid=616080). You can unpublish the extension by specifying the path to extension package file or by the extension name.

    The following example unpublishes an extension by using its extension package file path `.\MyExtension.app`. 

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

<!--  
### Get an overview of published extension
A server instance can have several published extensions, and  unpublishing the extensions requires that you provide specific information about the extension, like the name, version or path to extension package file. To get this information, you can run the the [Get-NAVAppInfo cmdlet](https://docs.microsoft.com/en-us/powershell/module/microsoft.dynamics.nav.apps.management/get-navappinfo) on the server instance:

```
Get-NAVAppInfo -ServerInstance YourDynamicsNAVServer
```

### Unpublish an extension
To unpublish the extension, run the [Unpublish-NAVApp cmdlet](https://go.microsoft.com/fwlink/?linkid=616080). You can unpublish the extension by specifying the path to extension package file or by the extension name.

The following example unpublishes an extension by using its extension package file path `.\MyExtension.app`. 

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
-->

## See Also  
[Publishing and Installing an Extension](devenv-how-publish-and-install-an-extension-v2.md)  
[Developing Extensions](devenv-dev-overview.md)