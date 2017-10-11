---
author: jswymer
title: "Upgrading an Extension V2 to a new version"
description: "Describes how to add code to upgrade data in a new extension version."
ms.custom: na
ms.date: 11/10/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
---
# Upgrading Extensions V2
This article provides information about how to make a newer version of extension upgrade available on tenants. The first phase of this process is to develop the extension for upgrading, which means adding code to upgrade data from the previous extension version. Once you have the upgrade code in place, you can run the upgrade for new version to get it published and installed.

> [!Note]
> An *upgrade* is defined as enabling an extension that has a greater version number, as defined in the app.json file, than the current installed extension version. 

## Developing an extension for upgrading
When developing a new extension version, you must consider to the data from the previous version, and any modifications that must be applied to the data to make it compatible with the current version. For example, it could be that the new version adds a new field that needs default values set for existing records or the new version adds new tables that must be linked to existing records. To address this type of data handling, you have to a write upgrade code for the extension version.

If there are no data changes between the versions of your extension, then you do not need to write upgrade code. All data that is not modified by upgrade code will automatically be restored. 

### Writing upgrade code
You write upgrade logic in an upgrade codeunit, which is a codeunit whose [SubType property](properties/devenv-subtype-property-codeunit.md) is set to **Upgrade**. An upgrade codeunit supports several system triggers on which you can add data upgrade code. These triggers are invoked when you run the data upgrade process on the new extension.

The upgrade codeunit becomes an integral part of the extension and can be modified as needed for subsequent version. You can have more than one upgrade codeunit. However, be aware that although there is a set order to the sequence of the upgrade triggers, there is no guarantee on the order of execution of the different codeunits. If you do use multiple upgrade units, make sure that they can run independent of each other.

### Upgrade triggers
The following tables describes the upgrade triggers and lists them in the order in which they are invoked.

|Trigger |Description | Fails the upgrade on error |
|--------|------------|------------------------|
|OnCheckPreconditionsPerCompany() or OnCheckPreconditionsPerDatabase()| Used to check that certain requirements are met in order to run the upgrade.|Yes|
|OnUpgradePerCompany() or OnUpgradePerDatabase()|Used to perform the actual upgrade.|Yes| 
|OnValidateUpgradePerCompany() or OnValidateUpgradePerDatabase()|Used to check that the upgrade was successful.|Yes|
|OnAfterUpgradeCommitPerCompany() or OnAfterUpgradeCommitPerDatabase()|Used to perform post-upgrade tasks after transactions in the previous triggers are committed.|No|

`PerCompany` triggers are run once for each company in the database, where each trigger is executed within its own system session for the company.

`PerDatabase` triggers are run executed once in the entire upgrade process, in a single system session that does not open any company.

### Upgrade codeunit syntax
The following code illustrates the basic syntax and structure of an upgrade codeunit:

```
codeunit [ID] [NAME]
{
	Subtype=Upgrade;
	
	trigger OnCheckPreconditionsPerCompany()
	begin
		// Code to make sure company is OK to upgrade.
	end;
	
	trigger OnUpgradePerCompany()
	begin
		// Code to perform company related table upgrade tasks
	end;
	
	trigger OnValidateUpgradePerCompany()
	begin
		// Code to make sure that upgrade was successful for each company
	end;
	
	procedure OnAfterUpgradeCommitPerCompany()
	begin
		// Code that performs  company related 'post-commit' tasks
	end;
}
```
> [!TIP]
> Use the shortcuts `tcodunit`and `ttrigger` to create the basic structure for the codeunit and trigger.

### Get information about an extension
Each extension version has a set of properties that contain information about the extension, including: AppVersion, DataVersion, Dependencies, Id, Name, and Publisher. This information can be useful when upgrading. For example, one of the more important properties is the `DataVersion` property, which tells you what version of data you are dealing with. These properties are encapsulated in a `ModuleInfo` data type. You can access these properties through `NAVApp.GetCurrentModuleInfo()` and `NAVAPP.GetCurrentModuleInfo()` methods.

### Upgrade codeunit example 
This example uses the `OnCheckPreconditionsPerDatabase()` trigger to check whether the data version of the previous extension version is compatible for the upgrade.

```
codeunit 70000001 MyUpgradeCodeunit
{
    Subtype=Upgrade;
    
    trigger OnCheckPreconditionsPerDatabase();
    var 
        myInfo : ModuleInfo;
    begin
        if NavApp.GetCurrentModuleInfo(myInfo) then
            if myInfo.DataVersion = Version.Create(1, 0, 0, 1) then
                ERROR('The upgrade is not compatible'); 
    end;
```

## Running the upgrade for the new extension version
To upgrade to the new extension version, you use the Sync-NAVApp and Start-NAVAppDataUpgrade cmdlets of the [!INCLUDE[nav_admin_md](includes/nav_admin_md.md)] to synchronize table schema changes in the extension with the SQL database and run the data upgrade code.

1.  Publish the new extension version. This example assumes the extension is not signed. This is not recommended in a production environment.

    ```
    Publish-NAVApp -ServerInstance DynamicsNAV -Path .\ProswareStuff_1.7.1.0.app -SkipVerification
    ```
    This validates the extension syntax against server instance, and stages it for synchronizing.

3.  Synchronize the new extension version with the database.

    ```
    Sync-NAVApp -ServerInstance DynamicsNAV -Name ProswareStuff -Version 1.7.1.0
    ```
    This synchronizes the database with any table schema changes in the extension; it adds the tables from the extension to the tenant.

4.  Run a data upgrade.

    ```
    Start-NAVAppDataUpgrade -ServerInstance DynamicsNAV -Name ProswareStuff -Version 1.7.1.0
    ```
    This runs the upgrade logic that is defined by the upgrade codeunits in the extension. This will uninstall the current extension version, and install the new version.

## See Also  
[Developing Extensions](devenv-dev-overview.md)  
[Getting Started](devenv-get-started.md) 
[How to: Publish and Install an Extension](devenv-how-publish-and-install-an-extension-v2.md)  
