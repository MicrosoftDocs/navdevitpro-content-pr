---
author: jswymer
title: "Writing extensions installation code"
description: "Describes how to add code to run to initialize data when an extension is installed."
ms.custom: na
ms.date: 11/30/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
redirect_url: /dynamics365/business-central/dev-itpro/developer/devenv-extension-install-code
---
# Writing Extension Install Code
There might certain operations outside of the extension code itself that you want performed when an extension is installed. These operations could include, for example, populating empty records with data, service callbacks and telemetry, version checks, and messages to users. To perform these types of operations, you write extension install code. Extension install code is run when:

-   An extension is installed for the very first time.
-   An uninstalled version is installed again.

This enables you to write different code for initial installation and reinstallation.

## How to write install code
You write install logic in an *install* codeunit. This is a codeunit that has the [SubType property](properties/devenv-subtype-property-codeunit.md) is set to **Install**. An install codeunit supports two system triggers on which you can add the install code.

|Trigger |Description |
|--------|------------|
|OnInstallAppPerCompany()|Includes code for company-related operations. Runs once for each company in the database.|
|OnInstallAppPerDatabase()|Includes code for database-related operations. Runs once in the entire install process.|

The install codeunit becomes an integral part of the extension version. You can have more than one install codeunit. However, be aware that there is no guarantee on the order of execution of the different codeunits. If you do use multiple upgrade units, make sure that they can run independent of each other.

### Install codeunit syntax
The following code illustrates the basic syntax and structure of an install codeunit:

```
codeunit [ID] [NAME]
{
	Subtype=Install;

	procedure OnInstallAppPerCompany()
	begin
		// Code for company related operations
	end;

	procedure OnInstallAppPerDatabase()
	begin
		// Code for database related operations
	end;

}
```
> [!TIP]
> Use the shortcuts `tcodunit` and `ttrigger` to create the basic structure for the codeunit and trigger.

### Get information about an extension
Each extension version has a set of properties that contain information about the extension, including: AppVersion, DataVersion, Dependencies, Id, Name, and Publisher. This information can be useful when installing. For example, one of the more important properties is the `DataVersion` property, which tells you what version of data you are dealing with. These properties are encapsulated in a `ModuleInfo` data type. You can access these properties by through the `NAVApp.GetCurrentModuleInfo()` and `NAVAPP.GetModuleInfo()` methods.

### Install codeunit example
This example uses the `OnCheckPreconditionsPerDatabase()` trigger to check whether the data version of the previous extension version is compatible for the upgrade.

```
codeunit 50100 MyInstallCodeunit
{
    Subtype=Install;

    trigger OnInstallAppPerDatabase();
    var
        myAppInfo : ModuleInfo;
    begin
        NavApp.GetCurrentModuleInfo(myAppInfo); // Get info about the currently executing module

        if myAppInfo.DataVersion = Version.Create(0,0,0,0) then // A 'DataVersion' of 0.0.0.0 indicates a 'fresh/new' install
            HandleFreshInstall
        else
            HandleReinstall; // If not a fresh install, then we are Re-installing the same version of the extension
    end;

    local procedure HandleFreshInstall();
    begin
        // Do work needed the first time this extension is ever installed for this tenant.
        // Some possible usages:
        // - Service callback/telemetry indicating that extension was install
        // - Initial data setup for use
    end;

    local procedure HandleReinstall();
    begin
        // Do work needed when reinstalling the same version of this extension back on this tenant.
        // Some possible usages:
        // - Service callback/telemetry indicating that extension was reinstalled
        // - Data 'patchup' work, for example, detecting if new 'base' records have been changed while you have been working 'offline'.
        // - Setup 'welcome back' messaging for next user access.
    end;
}

```

## See Also  
[Developing Extensions](devenv-dev-overview.md)  
[Getting Started with AL](devenv-get-started.md)  
[How to: Publish and Install an Extension](devenv-how-publish-and-install-an-extension-v2.md)  
[Converting Extensions V1 to Extensions V2](devenv-upgrade-v1-to-v2-overview.md)  
[Building Your First Sample Extension With Extension Objects, Install Code, and Upgrade Code](devenv-extension-example.md)  
