---
title: "How to: Publish and Install an Extension v2.0"
description: "Description of the process of publishing and installing an extension"
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 08/31/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: solsen
caps.latest.revision: 18
---

# How to: Publish and Install an Extension v2.0
To make your extension available to users, the package must be published to a specific Microsoft Dynamics NAV Server instance. The extension can be installed for one or more tenants.  

### To publish or remove an extension  

1.  In the Microsoft Dynamics NAV 2017 Administration Shell, use the `Publish-NAVApp` cmdlet. The cmdlet takes as parameters the server you want to install to and the .app package file that contains the extension. The following example publishes the extension MyExtension to the YourDynamicsNAVServer instance.  

    ```  
    Publish-NAVApp -ServerInstance YourDynamicsNAVServer -Path MyExtension.app  
    ```  

     Publish does more than just update internal tables. It also compiles the components of the extension behind-the-scenes and builds the necessary metadata objects that are used at runtime.  

     You can get an overview of the published extensions and their state using the `Get-NAVAppInfo` cmdlet. If no tenants have a specific extension installed, you can completely remove it using the `Unpublish-NAVApp` cmdlet.  

2.  In the Microsoft Dynamics NAV 2017 Administration Shell, use the `Unpublish-NAVApp` cmdlet. The cmdlet takes as parameters the server you want to remove the extension from, and the name of the extension. The following example removes the extension MyExtension from the YourDynamicsNAVServer instance.  

    ```  
    Unpublish-NAVApp -ServerInstance YourDynamicsNAVServer -Path MyExtension  
    ```  

 Once an app has been published, it must be made available for any tenant that wishes to use it.  

### To install an extension using PowerShell  

-   In the Microsoft Dynamics NAV 2017 Administration Shell, use the `Install-NAVApp` cmdlet. The following example installs the MyExtension for Tenant1 and Tenant3. In single-tenant deployments, you either specify default as the tenant ID, or you omit the *–Tenant* parameter.  

    ```  
    Install-NAVApp -ServerInstance YourDynamicsNAVServer -Name ”My Extension” –Tenant Tenant1, Tenant3  
    ```  

     Use `Get-NAVAppInfo –Tenant` command to get an overview of the extensions for that tenant, use the `Get-NAVAppTenant` cmdlet to get all tenants that have installed a specified extension, and uninstall an extension using the `Uninstall-NAVApp` cmdlet.  

    > [!NOTE]  
    >  When you uninstall an extension that includes tables and fields, this impacts the database schema and any data that the tables and fields contain.
    <!-- For more information, see [Extending Microsoft Dynamics NAV Using Extension Packages](Extending-Microsoft-Dynamics-NAV-Using-Extension-Packages.md).  -->

### To install an extension in the client  

1.  In [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)], open the **Extension Management** window to view the extensions that are published to your server. For each extension, you can see the current installation status.  
2.  Choose an extension to see additional information and to install the extension.  
3.  Review and accept the license agreement.  
4.  Choose the **Install** button to install the extension.      
5.  To uninstall an extension, choose the **Uninstall** action.  
    Alternatively, simply choose the extension. This opens the **Uninstall Extension** window.  

    > [!NOTE]  
    >  When you uninstall an extension that includes tables and fields, this impacts the database schema and any data that the tables and fields contain. For more information, see [Extending Microsoft Dynamics NAV Using Extension Packages](Extending-Microsoft-Dynamics-NAV-Using-Extension-Packages.md).  

## See Also  
[Developing Extensions](devenv-dev-overview.md)