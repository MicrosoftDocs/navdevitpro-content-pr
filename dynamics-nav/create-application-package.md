---
title: "Creating a Deployment Package"
ms.custom: na
ms.date: 28/01/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
author: jswymer
---
# Moving from On-premise to Online 
This article describes you can move your on-premise [!INCLUDE[navnow](includes/navnow_md.md)] solution that is application and tenants, to [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] online. 

## Prerequisites
To complete the tasks in this article, you will need the followingensure that you have the following:

-   Installation media (DVD) for the latest [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] version. 

    Download the version from [Microsoft Collaborate](https://developer.microsoft.com/en-us/dashboard/collaborate/packages).

-   [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] license.

-   A working environment of your current [!INCLUDE[navnow](includes/navnow_md.md)] application, including the following tools:
    -   [!INCLUDE[nav_dev_long](includes/nav_dev_long_md.md)]
    -   [!INCLUDE[nav_dev_shell_md](includes/nav_dev_shell_md.md)]
    -   [!INCLUDE[nav_shell_md](includes/nav_shell_md.md)]
    -   [!INCLUDE[nav_admin_md](includes/nav_admin_md.md)]
-    Microsoft SQL Server Management Studio installed.

     You must use SQL Server Management Studio 2012 Service Pack 1 or later. To download the latest version, see [Download SQL Server Management Studio](https://docs.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms).

## Upgrade your application
1. Complete a technical upgrade of your current application to the [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] version.

    This will convert your application database so that is runs on the new [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] platform. For more information, see [Converting a Database - Technical Upgrade](https://docs.microsoft.com/en-us/dynamics-nav/converting-a-database).

    > [!IMPORTANT]  
    >  Be sure to upload your [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] to converted database.
    >
    > After the technical upgrade, make sure that all the components are compiled successfully.

2. Optionally, upgrade your application to the new [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] application.

    You only have to complete this step if you want any new application features that are part of the latest [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] version.
    
    For more information, see [Upgrading the Application Code in Dynamics NAV](https://docs.microsoft.com/en-us/dynamics-nav/upgrading-the-application-code).

3. Complete the following steps as needed:
    
    1.  Import any new control add-ins that you want to use into the application database. 

        Import any client-side and server-side add-ins (such as control add-ins and .NET Framework Interoperability objects) which are not included by default into the old application database.
    
        For more information, see [To import the control add-in to the database](how-to--install-a-windows-client-control-add-in-assembly.md#InstallOnDatabase).

    2. Import test automation objects.
    3. Publish and synchronize any new V2 extensions that you want in application that are not already published.

        For more information, see [Publishing and Installing an Extension v2.0](devenv-how-publish-and-install-an-extension-v2).
    
4. Test and validate the upgraded application on-premise.


## Prepare the application and tenant databases

1. Separate the old database into two databases: the application database and the tenant database. 

    This step is only necessary if your database is not already separated into an application database and tenant database. 
    
    You do this by using the [!INCLUDE[nav_dev_shell_md](includes/nav_dev_shell_md.md)]. For more information, see [How to: Export the Application Tables to a Dedicated Database](how-to--export-the-application-tables-to-a-dedicated-database.md).

2.  For each database, remove all users except the default users like, dbo, guest, INFORMATION,SCHEMA, and sys. 

     Use SQL Server Management Studio to remove any previous database users that are assigned to these databases. This includes the service account that was used by the Microsoft Dynamics NAV Server to connect to the database (for example, the [NT AUTHORITY\NETWORK SERVICE] account).

3.  Clean up the system tables in the application and tenant databases.

    You must clean up certain system tables in these databases to ensure that that do not contain any records that are related to the previous deployment environment or activities.

    The following table lists the system tables in the application and tenant databases from which you must clear data.

    | Database | Table |Remarks|
    |----------|--------|-----|
    |Application|	dbo.Server Instance| |
    | |	dbo.$ndo$tenants|Note This table is only available if the original database was used in a multitenant environment.|
    | |dbo.Object Tracking |  |
    |Tenant|dbo.Access Control| |
    ||dbo.Active Session||
    ||dbo.Session Event||
    ||dbo.User||
    ||dbo.User Default Style Sheet||
    ||dbo.User Metadata||
    ||dbo.User Personalization||
    ||dbo.User Property||

    You can perform this work manually by using SQL Server Management Studio to connect to the databases and make the modifications directly. Or, you can use Windows PowerShell.

    To use Windows Powershell, you can run the following cmdlets:
 
    ```
    $DBServerInstance = ‘[YOUR SQL SERVER INSTANCE NAME]’  
    $DatabaseName = ‘[YOUR DB NAME]’

    Invoke-Sqlcmd –ServerInstance $DBServerInstance –Query “USE [$DatabaseName] DELETE FROM dbo.[Server Instance]” –Verbose | Write
    Invoke-Sqlcmd –ServerInstance $DBServerInstance –Query “USE [$DatabaseName] DELETE FROM dbo.[$(“$”)ndo$(“$”)cachesync]” –Verbose | Write
    ```

## Create the deployment package (.zip)
When you deploy your application online, you must provide a compressed .zip file that contains the application and tenant databases as data-tier application files, known as BACPAC (.bacpac) files. This article describes how you to create the BACPAC files and zip. You can do this using SQL Server Management Studio.

1.	In SQL Server Management Studio, connect to the server instance that hosts the application and tenant databases.
2.	In **Object Explorer**, right-click either the application or tenant database, choose **Task**, and then choose **xport Data-tier Application**.
3.	Follow the steps in the **Export Data-tier Application** wizard to export the database to a .bacpac file on your computer or network.

    You can use any name for the .bacpac file. 
4.  Repeat steps 2 and 3 for the other database.

    For more information about exporting databases to .bacpac format, see [Export a Data-tier Application](https://msdn.microsoft.com/en-us/library/Hh213241.aspx).

5. Create a ZIP (compressed) file that contains the application and tenant data base BACPAC files.

## See Also  
 [Configuring Database Components](Configuring-Database-Components.md)   
 [Configuring Microsoft SQL Server](Configuring-Microsoft-SQL-Server.md)
