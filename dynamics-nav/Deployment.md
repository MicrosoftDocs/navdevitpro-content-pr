---
title: "Deployment"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 0b0afe27-af2f-4172-b971-b4dd076d187a
caps.latest.revision: 31
manager: edupont
---
# Deployment
The topics in the Deployment node are intended to help an administrator install and configure [!INCLUDE[navnowlong](includes/navnowlong_md.md)] software.  

## Key Features of Setup  
 With [!INCLUDE[navnowlong](includes/navnowlong_md.md)] Setup, you can:  

- Install different components on different computers.  

- Choose from a selection of predefined [Installation Options](Installation-Options.md) or create your own custom list of components and options to install. For more information, see [How to: Choose Components to Install](How-to--Choose-Components-to-Install.md).  

- Preconfigure components before installation. For more information, see [How to: Preconfigure Components](How-to--Preconfigure-Components.md).  

- Create, save, or load Setup configuration files that capture your selection of components and configuration information. For more information, see [How to: Create or Load a Setup Configuration File](How-to--Create-or-Load-a-Setup-Configuration-File.md).  

  You use Setup to install software and to create custom deployments that you can distribute to different users across a company.  

## Installation Notes  

-   Before installing [!INCLUDE[navnowlong](includes/navnowlong_md.md)] components on a computer, you must remove \(uninstall\) any previous versions.  

-   All RoleTailored components must be from the same version and build of [!INCLUDE[navnow](includes/navnow_md.md)] for the software to run correctly.  

-   If you have either SQL Server 2000 or Microsoft SQL Server Desktop Engine \(MSDE\) installed on a computer where you want to install [!INCLUDE[navnow](includes/navnow_md.md)], then you must remove it before you begin installing. The presence of either of these database products causes a Setup error.
- [!INCLUDE[nav_dev_long](includes/nav_dev_long_md.md)]

  - Starting with Dynamics NAV 2018 cumulative update 41 and Dynamics NAV 2017cumulative update 54, the prerequisite SQL Server Native Client is no longer be installed by Setup or included on the installation media (DVD). This change doesn't affect the [!INCLUDE[nav_dev_long](includes/nav_dev_long_md.md)] installation if you upgrading from an earlier version, because the prerequisite should already have been installed. However, for a clean installation of the [!INCLUDE[nav_dev_long](includes/nav_dev_long_md.md)], you'll have to manually install the SQL Server Native Client; otherwise, you may experience problems connecting the [!INCLUDE[nav_dev_long](includes/nav_dev_long_md.md)] to the database. To install the SQL Server Native Client, follow these steps:

    1. Download an earlier cumulative update to the computer where you're installing [!INCLUDE[nav_dev_short](includes/nav_dev_short_md.md)].
      
       For Dynamics VAV 2018, go to [Released Cumulative Updates for Microsoft Dynamics NAV 2018](https://support.microsoft.com/en-us/topic/released-cumulative-updates-for-microsoft-dynamics-nav-2018-c469ba91-ee7a-ec06-e72a-6c8e331ea978)

       For Dynamics NAV 2017, go to [Released Cumulative Updates for Microsoft Dynamics NAV 2017](https://support.microsoft.com/en-us/topic/released-cumulative-updates-for-microsoft-dynamics-nav-2017-99f042ca-81ed-9fd5-2645-75fa9590dfd1)
    2. Unzip the files.
    3. Open the **DVD\Prerequisite Components\Microsoft SQL Server folder**, then double-click either the sqlncli.msi or sqlncli64.msi, depending on whether the computer has an 86-bit or 64-bit operating system respectively.
    4. Follow the instructions.


## See Also  
 [Product and Architecture Overview](Product-and-Architecture-Overview.md)   
 [Installation Options](Installation-Options.md)   
 [System Requirements for Microsoft Dynamics NAV](System-Requirements-for-Microsoft-Dynamics-NAV.md)   
 [Working with Microsoft Dynamics NAV Setup](Working-with-Microsoft-Dynamics-NAV-Setup.md)   
 [Configuring Microsoft Dynamics NAV](Configuring-Microsoft-Dynamics-NAV.md)
