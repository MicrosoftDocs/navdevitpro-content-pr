<properties
                pageTitle="Converting a Database | Dynamics NAV"
                description="Describes how perform a technical upgrade on a database."
                services=""
                documentationCenter=""
                authors="jswymer"/>
<tags
    ms.prod="dynamics-nav-2017"
    ms.topic="article"
    ms.devlang="na"
    ms.tgt_pltfrm="na"
    ms.workload="na"
    ms.date="06/16/2016"
    ms.author="jswymer" />

# Converting a Database

If your current solution is based on Dynamics NAV 2013, Dynamics NAV 2013 R2,  Dynamics NAV 2015, or Dynamics NAV 2015, you must convert the database to the  Dynamics NAV 91 technical requirements as part of the data upgrade process to Dynamics NAV 91 and then upgrade the application and data later. In this topic, the versions of Dynamics NAV prior to Dynamics NAV 91  are referred to as the old database.

Similarly, when you upgrade from one Dynamics NAV 91 cumulative update to the next cumulative update, you can be required to convert the database as described in task 2. This occurs when the cumulative update introduces changes to system tables. This type of database conversion is less complicated than the converting and old database.

**Warning:** You can choose to convert the old database and not upgrade your application. However, we recommend that you upgrade the application objects as well so that your solution includes important application fixes and new functionality that is introduced in Dynamics NAV 91. Upgrading the application will also reduce the amount of merging required to upgrade to the next major version of Dynamics NAV, bringing you to the latest version of the product faster.

**Important:** Before you start, make sure that you have applied the changes that are described in KB 2804640 "Code corrections for some Microsoft Dynamics NAV 2013 reports to prevent compilation errors with Report Viewer 2012 when upgrading to later versions of Microsoft Dynamics NAV".

To convert the old database to a Dynamics NAV 91 database, complete tasks 1 and 2. To convert the database from one cumulative update of MDynamics NAV 91 to the next cumulative update, complete task 2.

## Task 1: Preparing the Old Database
The first task is to back up the old database and then prepare to convert it.

1.  Make a copy of the old database or create full database backup.

    For more information, see Create a Full Database Backup (SQL Server).
2.  Clear all Microsoft Dynamics NAV Server instance records from the dbo.Server Instance table in the database on SQL Server.

    You can do this by using SQL Server Management Studio to open and clear the table.
3.  Open the development environment that matches the Dynamics NAV version of the old database, and then connect to the old database.

    For more information, see How to: Open Databases.
4.  In Object Designer, verify that no objects are locked.

    If one or more objects are locked, the conversion process cannot update the database version number. As a result, the conversion does not complete.

5.  On the **Tools** menu, choose **Build Server Application Objects**, and then choose the **Yes** button.

    **Note:** This step does not compile objects in the old database that have not been compiled before.
6.  If any errors occur, they are shown in the **Error List** window. Make sure that you address all compilation errors before you continue.

7.  Upload the Dynamics NAV 2016 Partner license to the database

    For more information, see Uploading a License File for a Specific Database.

    **Important:** The license that you upload must be a developer license. During the conversion, the development environment will convert the report objects that are stored in the old database to the RDL 2012 format.
8.  If you are converting a Dynamics NAV 2013 R2, Dynamics NAV 2015, or Dynamics NAV 2016 database, run the Sync-NavTenant cmdlet from the Dynamics NAV Administration Shell for the version to synchronize the database schema changes.

    For more information, see How to: Run the Sync-NAVTenant Cmdlet to Synchronize the Tenant Database with the Application Database.

## Task 2: Converting the Old Database
Next, you will convert the old database so that it can be used in Microsoft Dynamics NAV 2016.

## Prepare for the conversion
1. If the old database includes test runner codeunits, you must change the signature of the OnBeforeTestRun and OnAfterTestRun triggers of the test runner codeunits to include the TestPermission parameter, as shown in the following examples:

    ```
    OnBeforeTestRun(CodeunitID : Integer;CodeunitName : Text[30];FunctionName : Text[128]; TestPermissions : Text) Ok : Boolean)
    ```

    ```
    OnAfterTestRun(CodeunitID : Integer;CodeunitName : Text[30];FunctionName : Text[128]; FunctionTestPermissions : TestPermissions; Success : Boolean)
    ```
    If you do not change the signature, you will get errors when you compile these objects.

2.  Before you start the following procedure, you can choose to uninstall the old version of Dynamics NAV. When you uninstall Dynamics NAV, the database is still attached to the instance of SQL Server, which you can verify using SQL Server Management Studio.


**Tip:** If you want to write a script that helps you convert databases, you can use the Invoke-NAVDatabaseConversion function in the Dynamics NAV 91 Development Shell.

### Convert the database
1.  Install Dynamics NAV 91.

    Run the Dynamics NAV 91 Setup, and choose to install the **Developer** option.

2.  Open the Dynamics NAV 91 Development Environment, and then connect to the database that you prepared in the previous task.

    For more information, see How to: Open Databases.

3.  In the dialog box that appears, read the instructions carefully because this action cannot be reversed. When you are ready, choose the **OK** button, and then choose the **OK** button to confirm that you want to convert the database.

    Microsoft Dynamics NAV will now convert the database. This includes an upgrade of system tables, and an upgrade of all reports to support Report Viewer 2012.

4.  When you are notified that the conversion was successful, choose the **OK** button.

5.  Connect a Dynamics NAV 91 Server instance to the converted database.

    You use the Dynamics NAV 91 Server Administration tool to connect a Dynamics NAV 91 Server instance to the converted database.

    In addition, you must add the service account that is used by the server instance as a member of the db_owner role in the Dynamics NAV 91 database on SQL Server.

    For more information, see How to: Connect a Dynamics NAV 91 Server Instance to a Database and Giving the account necessary database privileges in SQL Server.

6.  Run the development environment as an administrator, and then set the development environment to use the Dynamics NAV 91 Server instance that connects to the database.

    For more information, see How to: Change the Dynamics NAV 91 Server Instance or Database Information.

7.  Run the schema synchronization to complete the database conversion.

    You can run the schema synchronization from the Dynamics NAV 91 Development Environment or Dynamics NAV 91 Administration Shell.

    **From the development environment:**

    Open development environment as an administrator. On the **Tools** menu, choose **Sync. Schema For All Tables**, and then choose **With Validation** and follow the schema synchronization instructions.

    **From the Dynamics NAV 91 Administration Shell:**

    Open the Dynamics NAV 91 Administration Shell as an administrator, and then run Sync-NavTenant cmdlet as follows:

    ```
    Sync-NavTenant -ServerInstance <ServerInstanceName>
    ```

    Replace <ServerInstanceName> with the name of the Dynamics NAV 91 Server instance that is connected to the database. For more information, see How to: Run the Sync-NAVTenant Cmdlet to Synchronize the Tenant Database with the Application Database.

8.  If the database references any assemblies (such as client control add-ins) that are not included on the Dynamics NAV 91 installation media (DVD), then add the assemblies to the **Add-ins** folder on Dynamics NAV 91 Server or Dynamics NAV 91 Windows client computers.

    For the Dynamics NAV 91 Windows client, the default path is C:\Program Files (x86)\Dynamics NAV 91\90\RoleTailored Client\Add-ins folder.

    For Dynamics NAV 91 Server, the default path is the C:\Program Files\Dynamics NAV 91\90\Service\Add-ins folder

9.  In the development environment, on the **Tools** menu, choose **Build Server Application Objects**, and then, in the dialog box, choose the **Yes** button.

10. Fix compilation errors.

    If any errors occur, they are shown in the **Error List** window. For information about compilation errors when you are converting a Microsoft Dynamics NAV 2013 database, see Compilation Errors When Converting a Microsoft Dynamics NAV 2013 Database.

    You can find all objects which did not compile in the **Object Designer** window, by setting a field filter on the **Compiled** field.

11. Upload the customer license to the converted database.

    For more information, see Uploading a License File for a Specific Database.

You have now completed the conversion of the Dynamics NAV 2013, Dynamics NAV 2013 R2, Dynamics NAV 2015, or Dynamics NAV 2016 database to be accessed from Dynamics NAV 91. To test the converted database, you can connect it to the Microsoft Dynamics NAV 2016 Server instance that by Microsoft Dynamics NAV clients, and then open a client.

Next, upgrade the application code to Microsoft Dynamics NAV 2016.

## See Also  
Upgrading the Application Code  
Upgrading the Data  
Automating the Upgrade Process using Sample Windows PowerShell Scripts  
Upgrading to Dynamics NAV 91  
