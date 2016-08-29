---
title: "Upgrading the Data"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: 34c5521d-10ca-47f5-bbab-4b03aa762b3c
caps.latest.revision: 43
manager: edupont
---
# Upgrading the Data
This topic describes the tasks required for upgrading a [!INCLUDE[nav7long](includes/nav7long_md.md)], [!INCLUDE[navsicily](includes/navsicily_md.md)], or [!INCLUDE[navcrete](includes/navcrete_md.md)] database to [!INCLUDE[navcorfu](includes/navcorfu_md.md)].  
  
 You use data conversion tools provided with [!INCLUDE[navcorfu](includes/navcorfu_md.md)] to convert the old data with the old version’s table and field structure, so that it functions together with the new version’s table and field structure.  
  
-   [Prerequisites](Upgrading-the-Data.md#Prereqs)  
  
-   [Task 1: Create a full SQL backup of the old database on SQL Server](Upgrading-the-Data.md#SQLBackup)  
  
-   [Task 2: Upload the Microsoft Dynamics NAV 2016 license to the old database](Upgrading-the-Data.md#UploadLicense)  
  
-   [Task 3: Delete all objects from the old database](Upgrading-the-Data.md#DeleteObjects)  
  
-   [Task 4: Uninstall the old product and install the new product](Upgrading-the-Data.md#UninstallOldProduct)  
  
-   [Task 5: Convert the old database to a Microsoft Dynamics NAV 2016 format](Upgrading-the-Data.md#ConvertDb)  
  
-   [Task 6: Connect a Microsoft Dynamics NAV 2016 Server instance to the converted database](Upgrading-the-Data.md#ConnectToServer)  
  
-   [Task 7: Run the schema synchronization to complete the database conversion](Upgrading-the-Data.md#RunSync1)  
  
-   [Task 8: Import the application objects to the converted database](Upgrading-the-Data.md#ImportAppObj)  
  
-   [Task 9: Run the schema synchronization to synchronize the new tables](Upgrading-the-Data.md#RunSync2)  
  
-   [Task 10: Run the data upgrade process](Upgrading-the-Data.md#RunStartNavUpgrade)  
  
-   [Task 11: Delete the upgrade objects](Upgrading-the-Data.md#DeleteUpgCodeunits)  
  
-   [Task 12: Import upgraded permission sets and permissions by using the Roles and Permissions XMLports](Upgrading-the-Data.md#ImportPerms)  
  
-   [Task 13: Set the language of the customer database](Upgrading-the-Data.md#SetLang)  
  
-   [Task 14: Add new control add-ins](Upgrading-the-Data.md#AddControlAddins)  
  
-   [Task 15: Import Payment Services and Data Encryption Key (Optional)](Upgrading-the-Data.md#UploadEncryptionKeys)  
  
> [!IMPORTANT]  
>  During the data upgrade, you must make sure that your computer uses the same codepage as the data. When you use conflicting codepages, some characters will not display in captions, and you might not be able to access the upgraded database.  
>   
>  Optionally, you can export the captions before the upgrade. For more information, see [How to: Add Translated Strings for Conflicting Text Encoding Formats](How%20to:%20Add%20Translated%20Strings%20for%20Conflicting%20Text%20Encoding%20Formats.md).  
  
 If you upgrade a database using a different codepage, [!INCLUDE[navnow](includes/navnow_md.md)] must remove incorrect metadata characters to complete the data upgrade. Then, you must open the database in the [!INCLUDE[nav_dev_short](includes/nav_dev_short_md.md)] on a computer with the relevant codepage and compile all objects. This adds the missing characters again.  
  
##  <a name="Prereqs"></a> Prerequisites  
  
-   A FOB file that contains the upgraded application code and upgrade toolkit. The upgrade toolkit can also be in a separate FOB file.  
  
     For more information, see [Upgrading the Application Code](Upgrading-the-Application-Code.md).  
  
-   All application objects in the old database have been built.  
  
     For more information, see [How to: Build Server Application Objects](How%20to:%20Build%20Server%20Application%20Objects.md).  
  
-   All application objects are unlocked.  
  
     For more information, see [How to: Unlock an Object](How%20to:%20Unlock%20an%20Object.md).  
  
-   The database schema has been synchronized in the old application.  
  
     For more information, see [How to: Run the Sync-NAVTenant Cmdlet to Synchronize the Tenant Database with the Application Database](How%20to:%20Run%20the%20Sync-NAVTenant%20Cmdlet%20to%20Synchronize%20the%20Tenant%20Database%20with%20the%20Application%20Database.md).  
  
-   All [!INCLUDE[nav_server](includes/nav_server_md.md)] instance records have been cleared from the **dbo.Server Instance** table in the old database in SQL Server.  
  
     You can do this by using SQL Server Management Studio to open and clear the table.  
  
-   Updated permission sets permissions XML files.  
  
-   \(Optional\) If the old [!INCLUDE[navnow](includes/navnow_md.md)] application uses [!INCLUDE[paymentsvcs](includes/paymentsvcs_md.md)], download the encryption key file that is used on the service connection.  
  
     You can download the encryption from the **\($ N\_825 DO Payment Connection Setup $\)** window in the [!INCLUDE[navnow](includes/navnow_md.md)] client. For more information, see [\($ N\_825 DO Payment Connection Setup $\)](assetId:///58e1ceda-e705-41f4-9f28-a027d8b816f9)  
  
-   \(Optional\) If the old [!INCLUDE[navnow](includes/navnow_md.md)] application uses data encryption, export the encryption key file that it used for the data encryption.  
  
     For more information, see [How to: Export and Import Encryption Keys](How%20to:%20Export%20and%20Import%20Encryption%20Keys.md).  
  
##  <a name="SQLBackup"></a> Task 1: Create a full SQL backup of the old database on SQL Server  
 You must create a full backup of the old database in the SQL Server. Alternatively, you can make a copy of the old database and perform the upgrade tasks on the copy.  
  
 For more information, see [Create a Full Database Backup \(SQL Server\)](http://msdn.microsoft.com/en-us/library/ms187510.aspx).  
  
##  <a name="UploadLicense"></a> Task 2: Upload the Microsoft Dynamics NAV 2016 license to the old database  
 By using the [!INCLUDE[nav_dev_long](includes/nav_dev_long_md.md)] that matches the old database, upload the [!INCLUDE[navcorfu](includes/navcorfu_md.md)] license to the database. For more information, see [Uploading a License File for a Specific Database](How%20to:%20Upload%20the%20License%20File.md#UploadtoDatabase).  
  
##  <a name="DeleteObjects"></a> Task 3: Delete all objects from the old database  
 In the [!INCLUDE[nav_dev_short](includes/nav_dev_short_md.md)] version that matches the database, open the old database, open Object Designer, and then delete all objects.  
  
##  <a name="UninstallOldProduct"></a> Task 4: Uninstall the old product and install the new product  
 Uninstall [!INCLUDE[nav7long](includes/nav7long_md.md)], [!INCLUDE[navsicily](includes/navsicily_md.md)], or [!INCLUDE[navcrete](includes/navcrete_md.md)], and then install [!INCLUDE[navcorfu](includes/navcorfu_md.md)].  
  
 During installation of [!INCLUDE[navcorfu](includes/navcorfu_md.md)], you can either choose the **Install Demo** option, for which you will discard the Demo database afterwards, or choose the Custom option, where you then select to install the Client \(with the Development Environment\), Server, and Administration Tool components.  
  
##  <a name="ConvertDb"></a> Task 5: Convert the old database to a Microsoft Dynamics NAV 2016 format  
 To convert the old database to a [!INCLUDE[navcorfu](includes/navcorfu_md.md)] format, open the old database in the [!INCLUDE[nav_dev_short](includes/nav_dev_short_md.md)], and follow the conversion instructions.  
  
##  <a name="ConnectToServer"></a> Task 6: Connect a Microsoft Dynamics NAV 2016 Server instance to the converted database  
 You use the [!INCLUDE[nav_admin](includes/nav_admin_md.md)] to connect a [!INCLUDE[nav_server](includes/nav_server_md.md)] instance to the converted database.  
  
 In addition, you must add the service account that is used by the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance as a member of the **db\_owner** role in the [!INCLUDE[navnow](includes/navnow_md.md)] database on SQL Server.  
  
> [!IMPORTANT]  
>  When upgrading a large database, you should increase the **SQL Command Timeout** setting for the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance, to avoid timeouts during schema synchronization. The default setting is 30 minutes.  
  
 For more information, see [How to: Connect a Microsoft Dynamics NAV Server Instance to a Database](How%20to:%20Connect%20a%20Microsoft%20Dynamics%20NAV%20Server%20Instance%20to%20a%20Database.md) and [Giving the account necessary database privileges in SQL Server](Provisioning-the-Microsoft-Dynamics-NAV-Server-Account.md#dbo).  
  
##  <a name="RunSync1"></a> Task 7: Run the schema synchronization to complete the database conversion  
 You can run the schema synchronization from the [!INCLUDE[nav_dev_long](includes/nav_dev_long_md.md)] or [!INCLUDE[nav_shell](includes/nav_shell_md.md)].  
  
 **From the [!INCLUDE[nav_dev_short](includes/nav_dev_short_md.md)]**:  
  
 Open [!INCLUDE[nav_dev_short](includes/nav_dev_short_md.md)] as an administrator. On the **Tools** menu, choose **Sync. Schema For All Tables**, and then choose **With Validation** and follow the schema synchronization instructions.  
  
 **From the [!INCLUDE[nav_shell](includes/nav_shell_md.md)]:**  
  
 Open the [!INCLUDE[nav_shell](includes/nav_shell_md.md)] as an administrator, and then run Sync-NavTenant cmdlet as follows:  
  
```  
Sync-NavTenant –ServerInstance <ServerInstanceName>  
```  
  
 Replace `<ServerInstanceName>` with the name of the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance that is connected to the database. For more information, see [How to: Run the Sync-NAVTenant Cmdlet to Synchronize the Tenant Database with the Application Database](How%20to:%20Run%20the%20Sync-NAVTenant%20Cmdlet%20to%20Synchronize%20the%20Tenant%20Database%20with%20the%20Application%20Database.md).  
  
##  <a name="ImportAppObj"></a> Task 8: Import the application objects to the converted database  
 In the [!INCLUDE[nav_dev_short](includes/nav_dev_short_md.md)], import all the application objects that you want in the [!INCLUDE[navcorfu](includes/navcorfu_md.md)] database. This includes the FOB file that contains all the [!INCLUDE[navcorfu](includes/navcorfu_md.md)] objects from the application code upgrade and upgrade toolkit objects.  
  
 When you import the FOB file, if you experience metadata conflicts, use the **Import Worksheet** to handle these conflicts.  
  
 Finally, on the dialog box for selecting the schema synchronization, set the **Synchronize Schema** option to **Later**.  
  
 If the upgrade toolkit objects are stored in a separate FOB file, then import the upgrade toolkit FOB file after the application objects are imported.  
  
##  <a name="RunSync2"></a> Task 9: Run the schema synchronization to synchronize the new tables  
 Similar to task 7, to publish the data schema changes of the newly imported tables to the SQL tables, run the **Sync. Schema For All Tables – With Validation** option from the [!INCLUDE[nav_dev_short](includes/nav_dev_short_md.md)] or run the Sync-NavTenant cmdlet from the [!INCLUDE[nav_shell](includes/nav_shell_md.md)].  
  
##  <a name="RunStartNavUpgrade"></a> Task 10: Run the data upgrade process  
 A data upgrade runs the upgrade toolkit objects, such as upgrade codeunits and upgrade tables, to migrate business data from the old table structure to the new table structure. You can start the data upgrade from the [!INCLUDE[nav_dev_long](includes/nav_dev_long_md.md)] or [!INCLUDE[nav_shell](includes/nav_shell_md.md)].  
  
> [!NOTE]  
>  In the last phase of data upgrade, all companies will be initialized by running codeunit 2 Company Initialization. This is done automatically. If you want to skip company initialization, then use the Start- NavDataUpgrade cmdlet and set the *SkipCompanyIntitialization* parameter.  
  
 **From the [!INCLUDE[nav_dev_short](includes/nav_dev_short_md.md)]**:  
  
 Open [!INCLUDE[nav_dev_short](includes/nav_dev_short_md.md)] as an administrator. On the **Tools** menu, choose **Data Upgrade**, and then choose **Start** and follow the instructions.  
  
 To view the progress of the data upgrade, on the **Tools** menu, choose **Data Upgrade**, and then choose **Show Progress**.  
  
 **From the [!INCLUDE[nav_shell](includes/nav_shell_md.md)]:**  
  
 Open the [!INCLUDE[nav_shell](includes/nav_shell_md.md)] as an administrator, and then run Start-NavDataUpgrade cmdlet as follows:  
  
```  
Start-NavDataUpgrade -ServerInstance <ServerInstanceName> -Force  
```  
  
 Replace `<ServerInstanceName>` with the name of the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance that is connected to the database.  
  
 To view the progress of the data upgrade, you can run Get-NavDataUpgrade cmdlet with the –Progress switch.  
  
 The data upgrade process runs CheckPreconditions and Upgrade functions in the upgrade codeunits. If any of the preconditions are not met or an upgrade function fails, you must correct the error and resume the data upgrade process. If CheckPreconditions and Upgrade functions are executed successfully, codeunit 2 is automatically run to initialize all companies in the database unless you set the *SkipCompanyIntitialization* parameter.  
  
##  <a name="DeleteUpgCodeunits"></a> Task 11: Delete the upgrade objects  
 At this point, you have upgraded the database to [!INCLUDE[navcorfu](includes/navcorfu_md.md)]. Now, you can delete the upgrade codeunits and upgrade table objects that you imported in task 8.  
  
 When you delete tables, on the **Delete** dialog box, set the **Synchronize Schema** option to **Force**.  
  
##  <a name="ImportPerms"></a> Task 12: Import upgraded permission sets and permissions by using the Roles and Permissions XMLports  
 You import the permission sets and permissions XML files according to the following procedure.  
  
#### To import the permission sets and permissions  
  
1.  Delete all permission sets in the database except the SUPER permission set.  
  
     In Object Designer, run page 9802 **Permission Sets**, and then delete the permission sets.  
  
2.  Run XMLport 9171 **Import\/Export Permission Sets** to import the permission sets XML file,  
  
     In the request page for the XMLport, in the **Direction** field, choose **Import**, choose the **OK** button, and then specify the permission sets XML file.  
  
3.  Run XMLport 9172 **Import\/Export Permissions** to import the permission XML file.  
  
     In the request page for the XMLport, in the **Direction** field, choose **Import**, choose the **OK** button, and then specify the permissions XML file.  
  
##  <a name="SetLang"></a> Task 13: Set the language of the customer database  
 In the [!INCLUDE[nav_dev_short](includes/nav_dev_short_md.md)], choose **Tools**, choose **Language**, and then select the language of the original customer database.  
  
##  <a name="AddControlAddins"></a> Task 14: Add new control add-ins  
 The database is now fully upgraded and is ready for use. However, you may want to add the new client control add-ins that are included in [!INCLUDE[navnowlong](includes/navnowlong_md.md)]. These are not added by the upgrade process. The following client control add-ins are available from the [!INCLUDE[navnow](includes/navnow_md.md)] product media:  
  
-   Microsoft.Dynamics.Nav.Client.BusinessChart  
  
-   Microsoft.Dynamics.Nav.Client.PageReady  
  
-   Microsoft.Dynamics.Nav.Client.PingPong  
  
-   Microsoft.Dynamics.Nav.Client.VideoPlayer  
  
-   Microsoft.Dynamics.Nav.Client.SocialListening  
  
 You can add control add-ins in the **Control Add-ins** window in the [!INCLUDE[nav_windows](includes/nav_windows_md.md)]. For more information, see [How to: Register a Windows Client Control Add-in](How%20to:%20Register%20a%20Windows%20Client%20Control%20Add-in.md).  
  
##  <a name="UploadEncryptionKeys"></a> Task 15: Import Payment Services and Data Encryption Key \(Optional\)  
  
-   If you want to set up Payment Services for Microsoft Dynamics ERP as before, you must upload the payment service encryption key file that was downloaded previously.  
  
     You upload the encryption key from the **\($ N\_825 DO Payment Connection Setup $\)** window in the [!INCLUDE[navnow](includes/navnow_md.md)] client. For more information, see [\($ N\_825 DO Payment Connection Setup $\)](assetId:///58e1ceda-e705-41f4-9f28-a027d8b816f9).  
  
-   If you want to use data encryption as before, you must import the data encryption key file that was exported previously.  
  
     For more information, see [How to: Export and Import Encryption Keys](How%20to:%20Export%20and%20Import%20Encryption%20Keys.md).  
  
## See Also  
 [Upgrading the Application Code](Upgrading-the-Application-Code.md)   
 [Automating the Upgrade Process using Sample Windows PowerShell Scripts](Automating-the-Upgrade-Process-using-Sample-Windows-PowerShell-Scripts.md)   
 [Synchronizing Table Schemas](Synchronizing-Table-Schemas.md)   
 [Upgrading to Microsoft Dynamics NAV 2016](Upgrading-to-Microsoft-Dynamics-NAV-2016.md)