---
title: "Demo Option"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 6a8d6302-714b-4af0-8019-970572a79a7b
caps.latest.revision: 32
manager: terryaus
---
# Demo Option
The **Install Demo** option is available on the first page after you accept the Microsoft Software License Terms in [!INCLUDE[navnowlong](../dynamics-nav/includes/navnowlong_md.md)] Setup. When you choose **Install Demo**, Setup installs all three tiers of the [Product and Architecture Overview](../dynamics-nav/Product-and-Architecture-Overview.md) on the local computer.  
  
 The Demo Install is intended for users who want to try the features of [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)]. We do not recommend this as the foundation for an actual production environment.  
  
> [!WARNING]  
>  You must install the Demo on a computer that uses a 64\-bit Windows operating system.  
  
## Demo Install Option Notes  
  
-   When you choose **Demo Install**, Setup begins to copy files. After this, you have no additional interaction with Setup. Choose **Close** to exit Setup when it is finished copying files.  
  
-   Setup installs SQL Server 2012 Express, creates a SQL Server instance, **NAVDEMO**, and installs the **Demo Database NAV \(9\-0\)** in this instance. Previous versions of [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] installed the Demo database in the default SQL Server instance.  
  
     The first time that you install [!INCLUDE[navnowlong](../dynamics-nav/includes/navnowlong_md.md)], the new SQL Server instance and Demo database are created automatically. If you subsequently delete [!INCLUDE[navnowlong](../dynamics-nav/includes/navnowlong_md.md)] and then run Setup to install the Demo version again, Setup prompts you to replace the existing database:  
  
     `The SQL Server Instance “NAVDEMO” already has an instanced named ‘Demo Database NAV (9-0)’. Would you like to replace this database?`  
  
     You can choose **OK** or **Cancel**.  
  
-   Setup cannot install the data file for a database, an .mdf file, to the local computer if the destination folder or drive is compressed.  
  
## Installed Components  
 When you choose the Demo Install option, Setup installs the following components:  
  
-   [!INCLUDE[nav_windows](../dynamics-nav/includes/nav_windows_md.md)].  
  
     For more information, see [Client Types](../dynamics-nav/Client-Types.md).  
  
-   [Microsoft Dynamics NAV Server](../dynamics-nav/Microsoft-Dynamics-NAV-Server.md).  
  
-   [Development Environment \(C\-SIDE\)](../dynamics-nav/Development-Environment--C-SIDE-.md).  
  
-   Microsoft Office Excel Add\-In.  
  
-   SQL Server Express 2012, a smaller\-scale version of SQL Server. If a valid version of SQL Server is already present on the computer where you are installing the Demo version, Setup does not install SQL Server Express 2012.  
  
-   [SQL Server Database Components](../dynamics-nav/SQL-Server-Database-Components.md).  
  
-   [!INCLUDE[demolong](../dynamics-nav/includes/demolong_md.md)], with a demo license. For information about what you can do with this license, see [Properties of the Demo License](../dynamics-nav/Properties-of-the-Demo-License.md).  
  
> [!NOTE]  
>  By default, the **Install Demo** option does not install the [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] Help Server or the [!INCLUDE[nav_web_server](../dynamics-nav/includes/nav_web_server_md.md)]. If you want these options, you can run the installation program again, choose the **Custom** option, and then choose the option that you want.  
  
## See Also  
 [System Requirements for Microsoft Dynamics NAV 2016](../dynamics-nav/System-Requirements-for-Microsoft-Dynamics-NAV-2016.md)   
 [Properties of the Demo License](../dynamics-nav/Properties-of-the-Demo-License.md)   
 [Client Types](../dynamics-nav/Client-Types.md)   
 [Installation Considerations for Microsoft SQL Server](../dynamics-nav/Installation-Considerations-for-Microsoft-SQL-Server.md)   
 [Custom Option](../dynamics-nav/Custom-Option.md)