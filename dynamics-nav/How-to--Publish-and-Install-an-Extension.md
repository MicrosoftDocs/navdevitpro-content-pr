---
title: "How to: Publish and Install an Extension"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: aee81285-2312-4cb1-8d51-3bf82c28806b
caps.latest.revision: 5
---
# How to: Publish and Install an Extension
To make your extension available to users, the package must be published to a specific [!INCLUDE[nav_server](includes/nav_server_md.md)] instance. The extension can be installed for one or more tenants.  
  
### To publish or remove an extension  
  
1.  In the [!INCLUDE[nav_shell](includes/nav_shell_md.md)], use the `Publish-NAVApp` cmdlet. The cmdlet takes as parameters the server you want to install to and the .navx package file that contains the extension. The following example publishes the extension MyExtension to the YourDynamicsNAVServer instance.  
  
    ```  
    Publish-NAVApp -ServerInstance YourDynamicsNAVServer -Path MyExtension.navx  
    ```  
  
     Publish does more than just update internal tables. It also compiles the components of the extension behind\-the\-scenes and builds the necessary metadata objects that are used at runtime.  
  
     You can get an overview of the published extensions and their state using the `Get-NAVAppInfo` cmdlet. If no tenants have a specific extension installed, you can completely remove it using the `Unpublish-NAVApp` cmdlet.  
  
2.  In the [!INCLUDE[nav_shell](includes/nav_shell_md.md)], use the `Unpublish-NAVApp` cmdlet. The cmdlet takes as parameters the server you want to remove the extension from, and the name of the extension. The following example removes the extension MyExtension from the YourDynamicsNAVServer instance.  
  
    ```  
    Unpublish-NAVApp -ServerInstance YourDynamicsNAVServer -Path MyExtension  
    ```  
  
 Once an app has been published, it must be made available for any tenant that wishes to use it.  
  
### To install an extension  
  
-   In the BROKEN-INCLUDE-nav_admin_shell, use the `Install-NAVApp` cmdlet. The following example installs the MyExtension for Tenant1 and Tenant3. In single\-tenant deployments, you either specify default as the tenant ID, or you omit the *–Tenant* parameter.  
  
    ```  
    Install-NAVApp -ServerInstance YourDynamicsNAVServer -Name ”My Extension” –Tenant Tenant1, Tenant3  
    ```  
  
     Use `Get-NAVAppInfo –Tenant` command to get an overview of the extensions for that tenant, use the `Get-NAVAppTenant` cmdlet to get all tenants that have installed a specified extension, and uninstall an extension using the `Uninstall-NAVApp` cmdlet.  
  
    > [!NOTE]  
    >  When you uninstall an extension that includes tables and fields, this impacts the database schema and any data that the tables and fields contain. For more information, see [Extending Microsoft Dynamics NAV Using Extension Packages](Extending-Microsoft-Dynamics-NAV-Using-Extension-Packages.md).  
  
## See Also  
 [Extending Microsoft Dynamics NAV Using Extension Packages](Extending-Microsoft-Dynamics-NAV-Using-Extension-Packages.md)   
 [How to: Develop an Extension](How%20to:%20Develop%20an%20Extension.md)   
 [How to: Create an Extension Package](How%20to:%20Create%20an%20Extension%20Package.md)   
 [Comparing and Merging Application Object Source Files](Comparing-and-Merging-Application-Object-Source-Files.md)   
 [Microsoft Dynamics NAV Windows PowerShell Cmdlets](Microsoft-Dynamics-NAV-Windows-PowerShell-Cmdlets.md)   
 [Administration Cmdlets for Microsoft Dynamics NAV](http://go.microsoft.com/fwlink/?LinkID=510540)
