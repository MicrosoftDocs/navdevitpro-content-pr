---
title: "Creating a Deployment Package"
author: edupont04
manager: edupont04
ms.custom: na
ms.date: 10/13/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
author: jswymer
---
# Moving from  Onpremise to Online 
This article describes you can move your on-premise [!INCLUDE[navnow](includes/navnow_md.md)] solution to [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] online. 

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

## Upgrade your current application
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


## Prepare the Application and Tenant Databases

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

<!-- 
## Prerequisites
You perform some of the tasks by using SQL Server Management Studio. You must use SQL Server Management Studio 2012 SP1 or later.
##Tasks
To prepare the databases, complete the following procedure.

2.	If the database is from an earlier Microsoft Dynamics NAV version than Microsoft Dynamics NAV 2016, convert the database to the Microsoft Dynamics NAV 2016 platform.

 You must convert the old database to comply with the Microsoft Dynamics NAV 2016 technical requirements. To convert the old database to a Microsoft Dynamics NAV 2016 format, open the old database in the Microsoft Dynamics NAV 2016 development environment, and follow the conversion instructions. For complete instructions, see [Converting a Database](http://go.microsoft.com/fwlink/?LinkID=626660).
 >**Note:** The old database does not need to include a Dynamics NAV 2016 license at this time, so you can skip the step for uploading the license. However, you will need a valid license file when you want to provision an application service that uses a version of the application.    
3.	Separate the converted database into an application database and a tenant database.

 For more information, see [How to: Export the Application Tables to a Dedicated Database](http://go.microsoft.com/fwlink/?LinkID=626654).

 This step is only necessary if your Microsoft Dynamics NAV database is not already separated into an application database and tenant database. Later, by using the Dynamics NAV Management Portal, you will upload the application database that you want to use for your application service together with a matching tenant template database to be deployed for each new tenant added to the application service.
4.	Upload your Microsoft Dynamics NAV license to the application database.

 If you did not do so during database conversion in step 2, upload the Microsoft Dynamics NAV license into the application database. For more information, see Uploading a License File for a Specific Database. This task is optional because you can also add a license to an application when you set it up in the Dynamics NAV Management Portal. The advantage of uploading the license at this time is that it acts as a default license.
5.	Clean up the system tables in the application and tenant database.

 For more information, see [Cleaning up the system tables in the application and tenant database](#cleaning-up-the-system-tables-in-the-application-and-tenant-databases).

6.	Remove users from the application and tenant databases.

 Use SQL Server Management Studio to remove any previous database users that are assigned to these databases, such as service account that was used by the Microsoft Dynamics NAV Server to connect to the database (for example, the [NT AUTHORITY\NETWORK SERVICE] account).
7.	Export the application and tenant databases to data-tier application files in BACPAC format.
You must have a .bacpac file for the application database and one for the tenant database.
For more information, see [Exporting an application or tenant database to a BACPAC file](#exporting-an-application-or-tenant-database-to-a-BACPAC-file) that follows.

##Cleaning up the system tables in the application and tenant databases
 After you have prepared your application and tenant databases, you must clean up certain system tables in these databases to ensure that that do not contain any records that are related to the previous deployment environment or activities. Additionally, you must remove any database users that are associated with the previous deployment, such as the Microsoft Dynamics NAV Server service account.

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

For example, follow these steps:

1. Open Windows PowerShell ISE as an Administrator.
Add similar cmdlets to clean up the listed tables and run them too.
2. Copy and paste the cmdlet code.
  * Replace [YOUR DB NAME] with the name of your application database and tenant database accordingly.
  * Replace [YOUR SQL SERVER INSTANCE NAME] with the name of the SQL Server instance that hosts the database.
3. Run the cmdlets.
-->

## Create the deployment package

When you deploy your application online, you must provide a compressed .zip file that contains the application and tenant databases as data-tier application files, known as BACPAC (.bacpac) files. This article describes how you to create the BACPAC files and zip. You can do this using SQL Server Management Studio.

### Export the application and tenant database to BACPAC files

1.	In SQL Server Management Studio, connect to the server instance that hosts the application and tenant databases.
2.	In **Object Explorer**, right-click either the application or tenant database, choose **Task**, and then choose **xport Data-tier Application**.
3.	Follow the steps in the **Export Data-tier Application** wizard to export the database to a .bacpac file on your computer or network.

    You can use any name for the .bacpac file. 
4.  Repeat steps 2 and 3 for the other database.

For more information about exporting databases to .bacpac format, see [Export a Data-tier Application](https://msdn.microsoft.com/en-us/library/Hh213241.aspx).

## Create a zip file 

## See Also  
 [Configuring Database Components](Configuring-Database-Components.md)   
 [Configuring Microsoft SQL Server](Configuring-Microsoft-SQL-Server.md)
