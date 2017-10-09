---
title: "Converting Extensions V1 to V2 Overview"
description: "Overview of the converting of extensions."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 09/22/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.author: solsen
---

[!INCLUDE[newdev_dev_preview](includes/newdev_dev_preview.md)]

# Converting Extensions V1 to Extensions V2 Overview
Extensions are a programming model where functionality is defined as an addition to existing objects and defines how they are different or modify the behavior of the solution. This article explains the steps involved in converting V1 extensions, written in C/SIDE. to V2 extensions; written using the AL Language extension for Visual Studio Code. The overall steps for the conversion are:

1.  Convert the source code from C/AL to the AL syntax.
2.  Complete the development of the extension in AL syntax.
3.  Write upgrade code to restore and modify data from the V1 Extension tables.
4.  Build the extension.
5.  Run the upgrade on the published extension. 

## Convert the source code from V1 to V2
To convert the source code, you must use the Txt2Al conversion tool. The Txt2Al conversion tool allows you to take existing application objects that have been exported in .txt format and convert them into the new .al format. The .al format is used when developing extensions for [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]. For more information about converting the source code, see [Txt2Al Conversion Tool](devenv-txt2al-tool.md).

<!-- see if Hunter's comments should be applied to the txt2al tool topic -->

## Complete the development of the extension
When the source code has been converted using the Txt2Al conversion tool, open the project folder in Visual Studio Code, and then modify or add code to the new version as needed. For more information about getting started with Visual Studio Code and the AL Language extension, see [Getting Started](devenv-get-started.md).

You will probably run into compilation errors, these can typically be due to:

-   Object IDs that have changed. The conversion tool tries to convert your code into the object ID range allowed for Extensions V2.
-   Field or control names look different; the AL syntax requires names, this means that no empty or default names are allowed.
-   Menusuites do not exist in Extensions V2.
-   .NET references are not allowed; there is no support for .NET types. Instead you must use the classes that replace .NET calls. For more information, see [Reference](devenv-reference-overview.md).

> [!IMPORTANT]
> In the app.json, keep the ID the same as in the V1 extension. Also, make sure to increase the version number. The version number has the format P.R.V.B. To increase the version number, you must increase the value of P, R, or V by at least one. 

> To use `NAVAPP.RestoreArchiveData()` method for upgrading, you must not change the IDs of the tables that are being restored; this means that tables from your V1 extension must have the same IDs in the V2 extensions. 

## Write upgrade code to move data from V1 Extensions
Just like with V1 extensions, you have to write code to handle data in tables during upgrade. Writing code for the V1-to-V2 extension upgrade is very similar to the code that you have been writing for V1 Extensions. The differences are:

-   Instead of adding code to normal codeunit, you write the  code in an upgrade codeunit, which is a codeunit whose [SubType property](properties/devenv-subtype-property-codeunit.md) is set to **Upgrade**.
-   Instead of adding code to the user-defined functions `OnNavAppUpgradePerDatabase()` or `OnNavAppUpgradePerCompany()`, you add code to any one of the following system triggers that are implicit in the syntax of upgrade codeunits. The triggers are listed in the order in which they run.

|Trigger |Description |
|--------|------------|
|OnCheckPreconditionsPerCompany() or OnCheckPreconditionsPerDatabase()| Used to check that certain requirements are met in order for to run.|
|OnUpgradePerCompany() or OnUpgradePerDatabase()|Used to run the actual upgrade work| 
|OnValidateUpgradePerCompany() or OnValidateUpgradePerDatabase()|Used to check that the upgrade was successful|
|OnAfterUpgradeCommitPerCompany() or OnAfterUpgradeCommitPerDatabase()|Used to perform post-upgrade tasks|

But similar to V1 extensions, all of the same NAVAPP.* system methods still work with V2 extensions, and can be called from any of the upgrade triggers. 

|Method |Description |
|--------|------------|
|`NAVAPP.DeleteArchiveData(70000000)`|Deletes the archived data from table 70000000.|
|`NAVAPP.GetArchiveRecordRef(70000000, archRef)`|Gets a record ref to the archived data from table 70000000.|
|`archVersion := NAVAPP.GetArchiveVersion()`|Gets the version of the archived data from the old extension.|
|`NAVAPP.RestoreArchiveData(70000000)`|Restores the data from the archive of table 70000000.|
 
Using this existing API, you can easily restore/move all of your data from the old V1 extension into the new V2 by running an upgrade. For example, a simple upgrade codeunit for restoring the V1 extension data for extension table `70000000` could be:

```
codeunit 70000001 MyExtensionUpgrade
{
    Subtype=Upgrade;

    trigger OnUpgradePerDatabase();
    begin
        NAVAPP.RestoreArchiveData(70000000);
    end;
}
```

> [!IMPORTANT]
> In order to use `NAVAPP.RestoreArchiveData()`, you must not change the IDs of the tables that are being restored; this means that tables from your V1 extension must have the same IDs in the V2 extensions. 

## Build the extension package
Press Ctrl+Shift+B to compile and build the extension complete with the application objects and upgrade codeunit.

## Run the upgrade process

The final task of the conversion is to publish the V2 extension, and the run the upgrade. The following steps use an example that upgrades a V1 extension that is called 'ProsewareStuff' and has the version '1.5.0.0.', and is published, installed, and populated with data. The V2 extension has the same name (and ID), but it has the version '1.5.1.0'. The [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance is called 'DynamicsNAV' and there is only one tenant. 

1.  Uninstall the V1 extension.

    ```
    Uninstall-NavApp -ServerInstance NAV -Name ProsewareStuff -Version 1.5.0.0
    ```
    This removes the tables from the SQL Server database and archives extension data.

    > [!IMPORTANT]
    > The V1 extension must be uninstalled before upgrading it to a V2 extension. 

2.  Publish the V2 extension. This example assumes the extension is not signed.
    ```
    Publish-NavApp -ServerInstance DynamicsNAV -Path .\ProswareStuff_1.5.1.0.app -SkipVerification
    ```
    This validates the extension syntax against server instance, and stages it for syncing.

3.  Synchronize the V2 extension with the database.

    ```
    Sync-NavApp -ServerInstance NAV -Name ProswareStuff -Version 1.5.1.0
    ```
    This adds tables from V2 extension to SQL Server database.

4.  Run the upgrade process to handle archived data from the V1 extension. 
    ```
    Start-NavAppDataUpgrade -ServerInstance NAV -Name ProfitMaker -Version 1.5.1.0
    ```
    This runs the upgrade logic defined by the upgrade codeunit in the extension.

5. (optional) Unpublish the V1 extension.

    ```
    Unpublish-NavApp -ServerInstance NAV -Name ProfitMaker -Version 1.5.0.0
    ```
    This removes the unused extension package from server.


## See Also
[Getting Started](devenv-get-started.md)  
[Keyboard Shortcuts](devenv-keyboard-shortcuts.md)    
[Developer Reference](devenv-reference-overview.md)  
