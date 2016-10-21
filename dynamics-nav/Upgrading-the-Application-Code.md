---
title: "Upgrading the Application Code"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.author: jswymer
manager: edupont
ms-prod: "dynamics-nav-2017"

---
# Upgrading the Application Code
Typically, customers want all the customizations that have been implemented in their existing [!INCLUDE[navnow](includes/navnow_md.md)] databases to be migrated to their new [!INCLUDE[navnowlong](includes/navnowlong_md.md)] databases. Depending on the version of [!INCLUDE[navnow](includes/navnow_md.md)] that a database is being upgraded from, the amount of code changes between the two versions is large or small. To upgrade the application code, you must merge code from different versions of the application. This merge process is known as a *code upgrade* or *application upgrade*. You must upgrade the application before you upgrade the data.  

## Application Upgrade Overview  
 During an upgrade, you have to identify which changes you have to make, you have to upgrade the application objects and the application code, and you might have to upgrade data so that it fits the new database schema.

You must analyze and process code changes by comparing and merging three separate versions of the [!INCLUDE[navnow](includes/navnow_md.md)] database:  

|Version|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|-------------|---------------------------------------|  
|*Original version*|This is the baseline version of the solution that you want to upgrade, such as the original release of [!INCLUDE[nav7long](includes/nav7long_md.md)] or [!INCLUDE[navcorfu](includes/navcorfu_md.md)].|  
|*Modified version*|This is the version that you want to upgrade, such as a customer's [!INCLUDE[nav7long](includes/nav7long_md.md)] or [!INCLUDE[navcorfu](includes/navcorfu_md.md)] database with customizations and add-on solutions.|  
|*Target version*|This is the target of the merge process that you want to upgrade your application to, such as the standard version of the [!INCLUDE[navnowlong](includes/navnowlong_md.md)] database.|  

 When you merge the application objects from these three versions, you can import the result into a new [!INCLUDE[navnowlong](includes/navnowlong_md.md)] database that then contains the upgraded application. At the end of the process, you export the merged [!INCLUDE[navnowlong](includes/navnowlong_md.md)] objects from this database to a .fob file that you will use during the data upgrade.  

 The following list describes the main steps of upgrading the application code:  

1.  Prepare the application object text files.  

2.  Merge versions.  

3.  Resolve conflicts  

4.  Import and compile the merged application objects.  

5.  Export all objects.  

### Ways of upgrading application code
You can use any tool or set of tools to help you compare and merge code.  [!INCLUDE[navnow](includes/navnow_md.md)] includes [!INCLUDE[wps_2](includes/wps_2_md.md)] cmdlets and sample scripts that can help you upgrade your application. The cmdlets are available through the [!INCLUDE[nav_dev_shell_md](includes/nav_dev_shell_md.md)], or by importing the Microsoft.Dynamics.NAV.Model.Tools.psd1 module into the Windows PowerShell Integrated Scripting Environment (ISE). You can find the sample scripts on the product installation media, in the *WindowsPowerShellScripts\ApplicationMergeUtilities* folder.
We recommend that you use these cmdlets and sample scripts because they can make it faster to merge most changes. For example, you can combine several steps in a command that uses a cmdlet such as the [Merge-NAVApplicationObject](https://go.microsoft.com/fwlink/?linkid=398884). The following section describes how you can use the Merge-NAVApplicationObject cmdlet and other [!INCLUDE[wps_2](includes/wps_2_md.md)] cmdlets. For more information, see [Comparing and Merging Application Object Source Files](Comparing-and-Merging-Application-Object-Source-Files.md).

For information about other ways of upgrading your code, see [Upgrading the Application Code](http://msdn.microsoft.com/en-us/library/dn271652\(v=nav.71\).aspx) for [!INCLUDE[navsicily](includes/navsicily_md.md)] in the MSDN Library.  

## Preparing the Application Text Files  
 The [!INCLUDE[navnow](includes/navnow_md.md)] cmdlets take text files as input. You must prepare three sets of text files that contain application objects as describes in the list above. You can export application objects to text files from the [!INCLUDE[nav_dev_short](includes/nav_dev_short_md.md)], or by running the [ExportObjects](ExportObjects.md) command. The following list describes the main steps of preparing the text files that you must provide as input for the application merge process.  

1.  Create four folders on the computer, and name them as follows:  

 -   **ORIGINAL**  

      This folder will be used to store the application objects from the baseline version, such as the original release of [!INCLUDE[nav7long](includes/nav7long_md.md)] or [!INCLUDE[navcorfu](includes/navcorfu_md.md)].  

 -   **MODIFIED**  

      This folder will be used to store the application objects from the modified version, such as the customer's database.  

 -   **TARGET**  

      This folder will be used to store the application objects from [!INCLUDE[navnowlong](includes/navnowlong_md.md)].  

 -   **RESULT**  

      This folder will be used to store the application objects that are the result of the application merge. It will also contain zero or more .CONFLICT files that describe conflicting code.  

2.  Export all application objects from the original version, such as the original [!INCLUDE[nav7long](includes/nav7long_md.md)] database. Do not export system tables, which have the IDs in the 2000000000 range. Name the file **OldBaseVersion.txt**, and then save the file in the ORIGINAL folder that you created earlier.  

     For example, the [!INCLUDE[nav_dev_shell_md](includes/nav_dev_shell_md.md)] includes a function, **Export-NAVApplicationObject**, that runs the [ExportObjects](ExportObjects.md) command. This means that you can run a command such as the following:  

    ```  
    Export-NAVApplicationObject –DatabaseServer MyServer –DatabaseName "Demo Database NAV (7-0)" –Path C:\Upgrade\ORIGINAL\OldBaseVersion.txt  
    ```  

3.  Export all  application objects, except system tables, from the modified version, such as the customer's customized [!INCLUDE[nav7long](includes/nav7long_md.md)] database. Name the file **OldCustomVersion.txt**, and then save the file in the MODIFIED folder that you created earlier.  

    > [!TIP]  
    >  In some cases, existing customizations might be irrelevant after the upgrade because they correspond to new functionality in [!INCLUDE[navnowlong](includes/navnowlong_md.md)].

4.  Export all application objects, except system tables, from the new base version, such as the original [!INCLUDE[navnowlong](includes/navnowlong_md.md)] database. Name the file **NewBaseVersion.txt**, and then save the file in the TARGET folder that you created earlier.  

Optionally, you can use the [Split-NAVApplicationObjectFile](https://go.microsoft.com/fwlink/?linkid=398885) cmdlet to split each text file into separate text files for each application object. This can make it easier to keep track of the process. The end result at this stage is three folders with one or more text files that contain the three sets of application objects that you want to merge.  

In certain scenarios, you can choose to use the [Compare-NAVApplicationObject](https://go.microsoft.com/fwlink/?linkid=398882) cmdlet to identify the changes between the existing customized application and the new application. You can then choose to use the [Update-NAVApplicationObject](https://go.microsoft.com/fwlink/?linkid=398886) cmdlet to apply all or some of the changes to the new version. For more information, see [How to: Compare and Update Application Object Source Files](How-to--Compare-and-Update-Application-Object-Source-Files.md). However, we recommend that you use the Merge-NAVApplicationObject  cmdlet in most cases. For more information, see [How to: Merge Application Changes](How-to--Merge-Application-Changes.md).  

## Merging Versions  
You must now merge the three sets of application objects to create the application for the new database.  

The sample scripts on the [!INCLUDE[navnow](includes/navnow_md.md)] product media provide examples of how you can use the [Merge-NAVApplicationObject](https://go.microsoft.com/fwlink/?linkid=398884) cmdlet to merge the three sets of application objects. The following example illustrates the type of command that you can run.  

```  
Merge-NAVApplicationObject -OriginalPath .\ORIGINAL -TargetPath .\TARGET -ModifiedPath .\MODIFIED -ResultPath .\RESULT  
```  

Depending on the number of objects that you are merging and the number of differences found, this can take a few seconds, a few minutes, or longer. The RESULT folder will contain a text file for each application object. The result of the merge is shown when the cmdlet completes, including a description of any application objects with conflicting code. These conflicts are stored in .CONFLICT files in the RESULT folder. You can import all objects in the RESULT folder into the new [!INCLUDE[navnowlong](includes/navnowlong_md.md)] database, or you can analyze the conflicts before you import the objects.  

## Handling Conflicts  
 Depending on the application that you are upgrading, you can choose to analyze the conflicting code before you import the merged objects into the [!INCLUDE[nav_dev_short](includes/nav_dev_short_md.md)]. The conflicts are shown in the merged text files but are also identified in .CONFLICT files in the RESULT folder. Subfolders then contain copies of the source files from the versions that have conflicting code. You can analyze the conflicts in any tool, make the relevant changes, and then run the merge operation again. Alternatively, you can import the merged files into the [!INCLUDE[nav_dev_short](includes/nav_dev_short_md.md)], and resolve the conflicts there. For more information, see [Handling Merge Conflicts](Handling-Merge-Conflicts.md).  

## Importing and Compiling Merged Objects  
After you have completed the merge, create a new (empty) [!INCLUDE[navnowlong](includes/navnowlong_md.md)] database for the new upgraded application. Make sure the database includes a valid [!INCLUDE[navnowlong](includes/navnowlong_md.md)] license.

With the database in place, import the new customized (merged) application objects into the database, and then compile all objects. You must resolve any compilation errors before you can continue. The text files with the merged application objects include successfully merged code, and code that is partially merged. You can import the partially merged objects into the [!INCLUDE[navnowlong](includes/navnowlong_md.md)] development environment and resolve the conflicts there.  

For example, the [!INCLUDE[nav_dev_shell_md](includes/nav_dev_shell_md.md)] and Microsoft.Dynamics.NAV.Model.Tools.psd1 module include a **Join-NAVApplicationObjectFile** cmdlet and a **Import-NAVApplicationObject** function. The **Join-NAVApplicationObjectFile** cmdlet combines multiple application object files into one text file. The **Import-NAVApplicationObject** function runs the [ImportObjects](ImportObjects.md) command to import an object file. This means that you can run a command such as the following:  

```  
Join-NAVApplicationObjectFile –Source C:\Upgrade\RESULT\*.txt -Destination C:\Upgrade\all-merged.txt   

Import-NAVApplicationObject –DatabaseServer MyServer –DatabaseName "My Upgraded App" –Path C:\Upgrade\all-merged.txt  
```  

In this example, you first join the many text files in the RESULT folder into a single file, which you then import into an existing, empty database. When you compile the objects, an error is thrown for each code conflict, and you can use the tools that are available in the [!INCLUDE[nav_dev_short](includes/nav_dev_short_md.md)] to resolve the conflicts.  

You now have a new database with a fully upgraded application.  

## Exporting All Objects  
Now, you must export all objects of the new database to an **objects.fob** file so that you can import them when performing the data upgrade. The export must include customized objects, upgraded reget-helpports, and all other [!INCLUDE[navnowlong](includes/navnowlong_md.md)] objects.  

This completes the upgrade of the application code. Next, you must upgrade the data in the database. For more information, see [Upgrading the Data](Upgrading-the-Data.md).  

## See Also  
[Upgrading the Data](Upgrading-the-Data.md)   
[Upgrading to Microsoft Dynamics NAV 2016](Upgrading-to-Microsoft-Dynamics-NAV-2016.md)  
[How to: Create Databases.md](How-to--Create-Databases.md)  
