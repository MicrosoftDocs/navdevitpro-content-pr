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
# Creating a Deployment Package

This topic describes how to prepare an application database and tenant database from a single Microsoft Dynamics NAV database for deployment on an application in the Dynamics NAV Management Portal.
The Dynamics NAV Management Portal provisions an application as a multitenant cloud service that consists of an application database and one or more tenant databases. The application database contains information about the Microsoft Dynamics NAV application that is served to customers. A tenant database is used by each tenant (customer) that is hosted on the application service, and it contains the customer-specific business data.
If not already done, you must divide your Microsoft Dynamics NAV database into an application database and a tenant database. If your database is from an earlier Microsoft Dynamics NAV, you must also convert it to Microsoft Dynamics NAV 2016.

To deploy a [!INCLUDE[navnow](includes/navnow_md.md)] database to Azure SQL Database, the database must be exported as a data-tier application \(DAC\) file, which is known as a .bacpac file. This can be performed by using SQL Server Manager, as described in this topic.  


## Prepare the application

1. Download the latest [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] version from [Microsoft Collaborate](https://developer.microsoft.com/en-us/dashboard/collaborate/packages).
2. Complete a technical upgrade of your current application database to the [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] version.

    This will upgrade your application so that is runs on the new platform. For more information, see [Converting a Database - Technical Upgrade](https://docs.microsoft.com/en-us/dynamics-nav/converting-a-database).

    > [!IMPORTANT]  
    >  After the technical upgrade, make sure that all the components are compiled successfully.

3. (optional) Upgrade your application to the new features of [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] application.

    For more information, see [Upgrading the Application Code in Dynamics NAV](https://docs.microsoft.com/en-us/dynamics-nav/upgrading-the-application-code).

4. Complete the following steps as needed:
    
    1.  Import any control add-ins that you want to use in your application into the database. 
    
        For more information, see [To import the control add-in to the database](how-to--install-a-windows-client-control-add-in-assembly.md#InstallOnDatabase).

    1.	Install any new add-ins in the database that you want in the application that are not currently installed.

        Import any client-side and server-side add-ins (such as control add-ins and .NET Framework Interoperability objects) which are not included by default into the old application database.

        You can perform this task by using the Control Add-ins page in a Dynamics NAV client or the New-NAVAddIn cmdlet in the Dynamics NAV Administration Shell.

        For more information, see [To import a .NET Framework assembly into the database](http://go.microsoft.com/fwlink/?LinkID=691836), [Automatic Deployment of Control Add-ins](http://go.microsoft.com/fwlink/?LinkID=691837), or [New-NAVAddin Cmdlet](http://go.microsoft.com/fwlink/?LinkID=521781).

    2. Import test automation objects.
    3. Publish and synchronize any V2 extensions that you want in application that are not already published.

        For more information, see [Publishing and Installing an Extension v2.0](devenv-how-publish-and-install-an-extension-v2).
    
5. Test and validate the upgraded application on-premise.

6. Separate the application data and the business data into two databases: the application database and the tenant database. 

    This step is only necessary if your Microsoft Dynamics NAV database is not already separated into an application database and tenant database. For more information, see [How to: Export the Application Tables to a Dedicated Database](how-to--export-the-application-tables-to-a-dedicated-database.md)



## Prepare the Databases

1.  In SQL Server Manager, for each database, remove all users except the default users like, dbo, guest, INFORMATION,SCHEMA, and sys. 

     Use SQL Server Management Studio to remove any previous database users that are assigned to these databases, such as service account that was used by the Microsoft Dynamics NAV Server to connect to the database (for example, the [NT AUTHORITY\NETWORK SERVICE] account).

# Preparing the Application and Tenant Databases


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

##Exporting an application or tenant database to a BACPAC file
An application or tenant database must be in data-tier application files in BACPAC format (.bacpac file) before you can import them to an application in Dynamics NAV Management Portal. You can export the databases to .bacpac files by using SQL Server Management Studio.
>**Important:** You must use SQL Server Management Studio 2012 Service Pack 1 or later. The reason for this is that earlier versions of SQL Server Management Studio store table data in .bacpac files in JSON format, which is not supported by the Dynamics NAV Management Portal. Later versions store data in BCP format, which is supported by the Dynamics NAV Management Portal.

To export a database to a BACPAC file, follow these steps:
1.	In SQL Server Management Studio, connect to the server instance that hosts the application and tenant databases.
2.	In Object Explorer, right-click the application database, choose Task, and then choose Export Data-tier Application.
3.	Follow the steps in the Export Data-tier Application wizard to export the application database to a .bacpac file on your computer or network.
You can use any name for the .bacpac file.

  For more information about exporting databases to .bacpac format, see [Export a Data-tier Application](https://msdn.microsoft.com/en-us/library/Hh213241.aspx).

## See Also  
 [Configuring Database Components](Configuring-Database-Components.md)   
 [Configuring Microsoft SQL Server](Configuring-Microsoft-SQL-Server.md)
