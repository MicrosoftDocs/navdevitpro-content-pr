---
author: jswymer
title: "How to: Write Extension Upgrade Code"
ms.custom: na
ms.date: 07/10/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
---
This topic provides information about how you can upgrade an existing extension after making changes.  Schema changes can only be additive. This allows multiple versions to exist on the same server simultaneously.


## What constitutes an upgrade
An *upgrade* is when you publish an extension that has a higher version number than the current published versions.  

You should not necessarily consider the upgrade of extensions as part of the upgrade process of the [!INCLUDE[navnow](includes/navnow_md.md)] deployment as a whole; unless a product upgrade has an adverse effect on an extension. In this case, you will need to address the condition by adding upgrade code to your extension. You can upgrade your extension independently of the [!INCLUDE[navnow](includes/navnow_md.md)] deployment.  

> [!TIP]  
>  We recommend that you add the upgrade code to your very first version of the extension to handle the uninstallation and reinstallation for cases when an upgrade failed, or the users inadvertently uninstalled.  

## Developing an Extension for Upgrading

You 
### Writing upgrade code for an extension
When developing a new extension version, you should consider the data that comes from an old extension version and any modifications that must be applied to make it compatible with the current version. This includes things like the new version has a new field that needs default values for existing records or the new version has new tables that must be linked to existing records.

You write the logic for handling this data in an upgrade codenit, which is a codeunit whose [SubType property] is set to **Upgrade**.  An upgrade codeunit supports several system triggers on which you can write the upgrade code. These triggers are invoked when you run a data upgrade on the new extension. The following tables lists the upgrade trigger in the order in whihh they are invoked. 

|Trigger |Description | Fails the upgrade on error |
|--------|------------|------------------------|
|OnCheckPreconditionsPerCompany() or OnCheckPreconditionsPerDatabase()| Used to check that certain requirements are met in order for to run the upgrade.|Yes|
|OnUpgradePerCompany() or OnUpgradePerDatabase()|Used to perform the actual upgrade.|Yes| 
|OnValidateUpgradePerCompany() or OnValidateUpgradePerDatabase()|Used to check that the upgrade was successful.|Yes|
|OnAfterUpgradeCommitPerCompany() or OnAfterUpgradeCommitPerDatabase()|Used to perform post-upgrade tasks after transactions in the previous triggers are committed.|No.|

`PerCompany` triggers are run one time for each company in the database, where each trigger is executed within its own system session for the company.

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

> [!IMPORTANT]  
>  You can use more than one codeunit to contain the upgrade functions. However, it is recommended that you use a single codeunit because this gives you more control over the execution order of the upgrade code.

You must include `OnNavAppUpgradePerDatabase` or `OnNavAppUpgradePerCompany` functions to your upgrade code. If these functions are not present at the time of creating the extension package and there are schema changes, the packaging will fail with an error. The installation of an extension package will also validate that all table changes are handled, and the following error occurs if they are not handled:

*The package contains changes to the database schema that are not handled in upgrade code.*

## Upgrading to a new extension version

1.  Publish the new extension version. This example assumes the extension is not signed, which is not recommend in a production environment.

    ```
    Publish-NAVApp -ServerInstance DynamicsNAV -Path .\ProswareStuff_1.7.1.0.app -SkipVerification
    ```
    This validates the extension syntax against server instance, and stages it for syncing.

3.  Synchronize the new extension version with the database.

    ```
    Sync-NAVApp -ServerInstance NAV -Name ProswareStuff -Version 1.7.1.0
    ```
    This synchronizes any table schema changes in the extension with the SQL database.

4.  Run a data upgrade.

    ```
    Start-NAVAppDataUpgrade -ServerInstance NAV -Name ProswareStuff -Version 1.5.1.0
    ```
    This runs the upgrade logic that is defined by the upgrade codeunits in the extension. The current extension version is uninstalled, and the new extension version is installed.

## See Also  
[Extending Microsoft Dynamics NAV Using Extension Packages](Extending-Microsoft-Dynamics-NAV-Using-Extension-Packages.md)  
[Upgrading Extensions](extensions-upgrading.md)  
[GETARCHIVEVERSION Function](GETARCHIVEVERSION-Function.md)  
[GETARCHIVERECORDREF Function](GETARCHIVERECORDREF-Function.md)  
[RESTOREARCHIVEDATA Function](restorearchivedata-function.md)  
[DELETEARCHIVEDATA Function](deletearchivedata-function.md)  
[How to: Develop an Extension](How-to--Develop-an-Extension.md)  
[How to: Create an Extension Package](How-to--Create-an-Extension-Package.md)  
[Comparing and Merging Application Object Source Files](Comparing-and-Merging-Application-Object-Source-Files.md)  
[Microsoft Dynamics NAV Windows PowerShell Cmdlets](Microsoft-Dynamics-NAV-Windows-PowerShell-Cmdlets.md)  
[Development Cmdlets for Microsoft Dynamics NAV](http://go.microsoft.com/fwlink/?LinkID=510540)  
[Development](development.md)  
