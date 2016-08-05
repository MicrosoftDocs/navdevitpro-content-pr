<properties
                pageTitle="Upgrading the Data | Dynamics NAV"
                description="Describes how upgrade the data in an old database to Dynamics NAV."
                services=""
                documentationCenter=""
                authors="jswymer"/>
<tags
    ms.prod="dynamics-nav-2017"
    ms.topic="article"
    ms.devlang="na"
    ms.tgt_pltfrm="na"
    ms.workload="na"
    ms.date="07/05/2016"
    ms.author="jswymer" />

# Converting a Database

This topic describes the tasks required for upgrading a Dynamics NAV 2013, Dynamics NAV 2013 R2, Dynamics NAV 2015, or Dynamics NAV 2016 database to Dynamics NAV 2017.

You use data conversion tools provided with Dynamics NAV 2017 to convert the old data with the old version’s table and field structure, so that it functions together with the new version’s table and field structure.

**Important:** During the data upgrade, you must make sure that your computer uses the same codepage as the data. When you use conflicting codepages, some characters will not display in captions, and you might not be able to access the upgraded database.

Optionally, you can export the captions before the upgrade. For more information, see [How to: Add Translated Strings for Conflicting Text Encoding Formats](languages-howaddtranslatedstrings.md).

If you upgrade a database using a different codepage, Dynamics NAV 2017 must remove incorrect metadata characters to complete the data upgrade. Then, you must open the database in the development environment on a computer with the relevant codepage and compile all objects. This adds the missing characters again.

## Prerequisites
Before you convert the database, make sure that the following prerequisites are met:

-   A FOB file that contains the upgraded application code and upgrade toolkit. The upgrade toolkit can also be in a separate FOB file.

    For more information, see [Upgrading the Application Code](upgrade-upgradingapplicationcode.md).

-   All application objects in the old database have been built.

    For more information, see [How to: Build Server Application Objects](administration-howbuildserverapplicationobjects.md).

-   All application objects are unlocked.

    For more information, see [How to: Unlock an Object](objects-unlockobject.md).

-   The database schema has been synchronized in the old application.

    For more information, see [How to: Run the Sync-NAVTenant Cmdlet to Synchronize the Tenant Database with the Application Database](administration-howrunsynctenantcmdlet.md).

-   All Dynamics NAV 91 Server instance records have been cleared from the dbo.Server Instance table in the old database in SQL Server.

    You can do this by using SQL Server Management Studio to open and clear the table.

-   Updated permission sets permissions XML files.
-   If the old database includes test runner codeunits, you must change the signature of the OnBeforeTestRun and OnAfterTestRun triggers of the test runner codeunits to include the TestPermission parameter, as shown in the following examples:

    ```
    OnBeforeTestRun(CodeunitID : Integer;CodeunitName : Text[30];FunctionName : Text[128]; TestPermissions : Text) Ok : Boolean)
    ```

    ```
    OnAfterTestRun(CodeunitID : Integer;CodeunitName : Text[30];FunctionName : Text[128]; FunctionTestPermissions : TestPermissions; Success : Boolean)
    ```

-   (Optional) If the old Microsoft Dynamics NAV application uses Payment Services for Microsoft Dynamics ERP, note that this is discontinued in Dynamics NAV 2017.
<!-- DOL is discontinued. You can download the encryption from the Microsoft Dynamics ERP Payment Services Connection Setup window in the Microsoft Dynamics NAV client. For more information, see Microsoft Dynamics ERP Payment Services Connection Setup -->

-   (Optional) If the old Microsoft Dynamics NAV application uses data encryption, export the encryption key file that it used for the data encryption.

    For more information, see How to: Export and Import Encryption Keys.

## Task 1: Create a full SQL backup of the old database on SQL Server
You must create a full backup of the old database in the SQL Server. Alternatively, you can make a copy of the old database and perform the upgrade tasks on the copy.

For more information, see [Create a Full Database Backup (SQL Server)](http://msdn.microsoft.com/en-us/library/ms187510.aspx).

## Task 2: Upload the Dynamics NAV 2016 license to the old database
By using the Dynamics NAV Development Environment that matches the old database, upload the Dynamics NAV 91 license to the database. For more information, see Uploading a License File for a Specific Database.

## Task 3: Delete all objects from the old database
<!-- Anca is investigating whether this task should be moved after Task 7. 5. AUG: Eva added note about not deleting tables as per Collaboration Request 379698. -->
In the development environment version that matches the database, open the old database, open Object Designer, and then delete all objects except tables.

## Task 4: Uninstall the old product and install the new product
Uninstall Dynamics NAV 2013, Dynamics NAV 2013 R2, or  Dynamics NAV 2015, or Dynamics NAV 2016, and then install Dynamics NAV 2017.

During installation of Dynamics NAV 2017, you can either choose the **Install Demo** option, for which you will discard the Demo database afterwards, or choose the **Custom** option, where you then select to install the **Client** (with the Development Environment), **Server**, and **Administration Tool** components.

##Task 5: Convert the old database to a Dynamics NAV 2017 format
To convert the old database to a Dynamics NAV 2017 format, open the old database in the development environment, and follow the conversion instructions.  

## Task 6: Connect a Dynamics NAV 2017 Server instance to the converted database
You use the Dynamics NAV 91 Server Administration tool to connect a server instance to the converted database.

In addition, you must add the service account that is used by the server instance as a member of the **db_owner** role in the Dynamics NAV 2017 database on SQL Server.

**Important:**  When upgrading a large database, you should increase the SQL Command Timeout setting for the Dynamics NAV 2017 Server instance, to avoid timeouts during schema synchronization. The default setting is 30 minutes.

For more information, see [How to: Connect a Dynamics NAV Server Instance to a Database](upgrade-howconnectserverinstancedatabase.md) and [Giving the account necessary database privileges in SQL Server](deployment-provisioningserveraccount#giving-the-account-necessary-database-privileges-in SQL-Server).  

<!-- Added by Eva by request from Gerard Conroy-->
Before you continue, you must compile the system tables, including validation.  

## Task 7: Run the schema synchronization to complete the database conversion
You can run the schema synchronization from the Dynamics NAV 2017 Development Environment or Administration Shell.

From the development environment:

Open development environment as an administrator. On the **Tools** menu, choose **Sync. Schema For All Tables**, choose **With Validation**, and then follow the schema synchronization instructions.

From the Administration Shell:

Open the Dynamics NAV 2017 Administration Shell as an administrator, and then run Sync-NavTenant cmdlet as follows:

```
Sync-NavTenant -ServerInstance <ServerInstanceName>
```

Replace <ServerInstanceName> with the name of the Dynamics NAV 2017 Server instance that is connected to the database. For more information, see [How to: Run the Sync-NAVTenant Cmdlet to Synchronize the Tenant Database with the Application Database](administration-howrunsynctenantcmdlet.md).

## Task 8: Import the application objects to the converted database
In the development environment, import all the application objects that you want in the Dynamics NAV 91 database. This includes the FOB file that contains all the Dynamics NAV 2017 objects from the application code upgrade and upgrade toolkit objects.

When you import the FOB file, if you experience metadata conflicts, use the **Import Worksheet** to handle these conflicts.

Finally, on the dialog box for selecting the schema synchronization, set the **Synchronize Schema** option to **Later**.

If the upgrade toolkit objects are stored in a separate FOB file, then import the upgrade toolkit FOB file after the application objects are imported. You can find the default upgrade toolkit objects in the  **UpgradeToolKit** folder on the Dynamics NAV 91 installation media (DVD).

##Task 9: Run the schema synchronization to synchronize the new tables
Similar to task 7, to publish the data schema changes of the newly imported tables to the SQL tables, run the **Sync. Schema For All Tables - With** option from the development environment or run the Sync-NavTenant cmdlet from the Dynamics NAV  Administration Shell.

## Task 10: Run the data upgrade process
A data upgrade runs the upgrade toolkit objects, such as upgrade codeunits and upgrade tables, to migrate business data from the old table structure to the new table structure. You can start the data upgrade from the development environment or Administration Shell.

**Note:** In the last phase of data upgrade, all companies will be initialized by running codeunit 2 **Company Initialization**. This is done automatically. If you want to skip company initialization, then use the Start- NavDataUpgrade cmdlet and set the *SkipCompanyIntitialization* parameter.

From the development environment:

Open development environment as an administrator. On the **Tools** menu, choose **Data Upgrade**, choose **Start**, and then follow the instructions.

To view the progress of the data upgrade, on the **Tools** menu, choose **Data Upgrade**, and then choose **Show Progress**.

From the Administration Shell:

Open the Dynamics NAV 91 Administration Shell as an administrator, and then run Start-NavDataUpgrade cmdlet as follows:

```
Start-NavDataUpgrade -ServerInstance <ServerInstanceName> -Force
```

Replace <ServerInstanceName> with the name of the Microsoft Dynamics NAV Server instance that is connected to the database.

To view the progress of the data upgrade, you can run Get-NavDataUpgrade cmdlet with the -Progress switch.

The data upgrade process runs CheckPreconditions and Upgrade functions in the upgrade codeunits. If any of the preconditions are not met or an upgrade function fails, you must correct the error and resume the data upgrade process. If CheckPreconditions and Upgrade functions are executed successfully, codeunit 2 is automatically run to initialize all companies in the database unless you set the SkipCompanyIntitialization parameter.

## Task 11: Delete the upgrade objects
At this point, you have upgraded the database to Dynamics NAV 2017. Now, you can delete the upgrade codeunits and upgrade table objects that you imported in task 8.

When you delete tables, on the Delete dialog box, set the **Synchronize Schema** option to **Force**.

## Task 12: Import upgraded permission sets and permissions by using the Roles and Permissions XMLports
You import the permission sets and permissions XML files according to the following procedure.

**To import the permission sets and permissions**
1.  Delete all permission sets in the database except the **SUPER** permission set.

    In Object Designer, run page 9802 **Permission Sets**, and then delete the permission sets.
2.  Run XMLport 9171 **Import/Export Permission Sets** to import the permission sets XML file.

    In the request page for the XMLport, in the **Direction** field, choose **Import**, choose the **OK** button, and then specify the permission sets XML file.
3.  Run XMLport 9172 Import/Export Permissions to import the permission XML file.

    In the request page for the XMLport, in the Direction field, choose Import, choose the OK button, and then specify the permissions XML file.

## Task 13: Set the language of the customer database
In the development environment, choose **Tools**, choose **Language**, and then select the language of the original customer database.

## Task 14: Add new control add-ins
The database is now fully upgraded and is ready for use. However, you may want to add the new client control add-ins that are included in Dynamics NAV 2017. These are not added by the upgrade process. The following client control add-ins are available from the product installation media:

-   Microsoft.Dynamics.Nav.Client.BusinessChart
-   Microsoft.Dynamics.Nav.Client.PageReady
-   Microsoft.Dynamics.Nav.Client.PingPong
-   Microsoft.Dynamics.Nav.Client.VideoPlayer
-   Microsoft.Dynamics.Nav.Client.SocialListening

You can add control add-ins in the **Control Add-ins** window in the Dynamics NAV 91 client. For more information, see [How to: Register a Windows Client Control Add-in](controladdins-howregisterwindowsclientcontroladdin.md).

<!-- deprecated ## Task 15: Import Payment Services and Data Encryption Key (Optional)
If you want to set up Payment Services for Microsoft Dynamics ERP as before, you must upload the payment service encryption key file that was downloaded previously.

You upload the encryption key from the Microsoft Dynamics ERP Payment Services Connection Setup window in the Microsoft Dynamics NAV client. For more information, see Microsoft Dynamics ERP Payment Services Connection Setup.-->

If you want to use data encryption as before, you must import the data encryption key file that was exported previously.

For more information, see [How to: Export and Import Encryption Keys](dataencryption-howexportimportencryptionkeys.md).

##See Also  
[Upgrading the Application Code](upgrade-upgradingapplicationcode.md)  
 [Automating the Upgrade Process using Sample Windows PowerShell Scripts](upgrade-automatingupgradeprocess.md)  
[Synchronizing Table Schemas](tables-synchronizingtableschemas.md)  
[Upgrading to Dynamics NAV 91](upgrade-intro.md)
