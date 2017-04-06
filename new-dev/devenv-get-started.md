---
title: "Getting Started"
description: "Description of how to get started with the new development environment"
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 12/30/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: SusanneWindfeldPedersen
caps.latest.revision: 18
---

[!INCLUDE[dyn_fin_dev_preview](../dynamics-nav/includes/devenv_dev_preview.md)]

# Getting Started
To get started writing extensions for [!INCLUDE[navnow_md](includes/navnow_md.md)] you will need a [!INCLUDE[navnow_md](includes/navnow_md.md)] tenant, and Visual Studio Code. Visual Studio Code is a cross platform editor that you will use for coding and debugging. For the preview, you will download a VM (virtual machine) from the Microsoft Azure Gallery. The VM is set up for trying out the new development environment.

## Steps
1) First, you will need an Azure subscription. You can sign up for a [free subscription](https://azure.microsoft.com/en-us/free/).   
2) Go to [Microsoft Azure Marketplace](https://ms.portal.azure.com/#blade/Microsoft_Azure_Marketplace/GalleryFeaturedMenuItemBlade/selectedMenuItemId/home) and search for **Microsoft Dynamics NAV Developer Preview**.  
3) Follow the instructions to deploy and run.   
4) When you have a virtual machine set up, you will see a welcome text and here you can choose to try out the developer preview following the instructions on the screen.

# Getting started with Visual Studio Code
With the developer preview, you get sample code that compiles and runs by following a few steps.  

1) In Visual Studio Code, press **Ctrl**+**Shift**+**P** to show all commands.  
2) Type **AL: Go** (case-insensitive) and select a project folder.  

You now have a HelloWorld sample that compiles and runs. The JSON files in the project are automatically updated with the settings that allows you to press **F5** to build and deploy the solution. 

> [!NOTE] If symbols are missing, you will be prompted to download them.

## JSON file settings
The following table describes the settings in the JSON files.

Settings in the ```app.json``` file:

|Setting|Mandatory|Value|
|-------|---------|-----|
|id|Yes|The unique ID of the extension. When app.json file is automatically created, the ID is set to a new GUID value.|
|name|Yes|The unique extension name.|
|publisher|Yes|The name of your publisher, for example: **NAV Partner**, **LLC** |
|application|Yes, if base application objects are extended or referenced |The minimum supported version and locale of the base application to extend, for example: ```{  "version": "10.0.0.0",  "locale": "W1"  }```|
|platform|Yes, if system tables are referenced in the extension|The minimum supported version of the platform symbol package file, for example: "10.0.0.0". See the **List of objects in the platform symbol file section** below for the list of object symbols contained in the platform symbol package file.|
|packageCachePath|Yes, if base application is extended or system tables are referenced| The path to the folder where referenced symbol package files are located. The path could either be absolute or relative to the current extension working directory, for example: "../../resources"|

Settings in the ```launch.json``` file:

|Setting|Mandatory|Value|
|-------|---------|-----|
|server|Yes, if connecting to an on-premises server|The HTTP URL of your server, for example: http://localhost|
|serverInstance|Yes, if connecting to an on-premises server|The instance name of your server, for example: NAV|
|port|No|The port on which the development endpoint is running on the server, default value: 7049|
|tenant|No|The tenant ID in case the server is configured for multitenancy.|
|windowsAuthentication|No|Specifies whether Windows or Azure authentication should be used for publishing the extension. Currently only Windows authentication is supported.|
|startupObjectId|No|The ID of the startup object to launch when you press F5. Currently only objects of type Page are supported.|


## List of objects in the platform symbol file
The following table lists object symbols contained in the platform symbol package file. If the symbols are not present, you will prompted to download them.

### System tables

|Name|
|----|
|Access Control.al|
|Active Session.al|
|Add-in.al|
|Chart.al|
|Company.al|
|Configuration Package File.al|
|Debugger Breakpoint.al|
|Debugger Watch.al|
|Device.al|
|Document Service.al|
|Entitlement Set.al|
|Entitlement.al|
|License Permission.al|
|Media Set.al|
|Media.al|
|Membership Entitlement.al|
|NAV App Capabilities.al|
|NAV App Data Archive.al|
|NAV App Dependencies.al|
|NAV App Installed App.al|
|NAV App Object Metadata.al|
|NAV App Object Prerequisites.al|
|NAV App Tenant Add-In.al|
|NAV App Tenant App.al|
|NAV App.al|
|Object Metadata.al|
|Object Options.al|
|Object Tracking.al|
|Object.al|
|OData Edm Type.al|
|Page Data Personalization.al|
|Page Documentation.al|
|Permission Set.al|
|Permission.al|
|Profile Metadata.al|
|Profile.al|
|Record Link.al|
|Scheduled Task.al|
|Send-To Program.al|
|Server Instance.al|
|Session Event.al|
|Style Sheet.al|
|Tenant License State.al|
|Tenant Media Set.al|
|Tenant Media Thumbnails.al|
|Tenant Media.al|
|Tenant Permission Set.al|
|Tenant Permission.al|
|Tenant Web Service.al|
|Token Cache.al|
|User Default Style Sheet.al|
|User Metadata.al|
|User Personalization.al|
|User Property.al|
|User.al|
|Web Service.al|
|Webhook Notification.al|
|Webhook Subscription.al|

### Virtual tables
|Name|
|----|
|Aggregate Permission Set.al|
|AllObj.al|
|AllObjWithCaption.al|
|Automation Server.al|
|Code Coverage.al|
|CodeUnit Metadata.al|
|Database Locks.al|
|Database.al|
|Date.al|
|Debugger Call Stack.al|
|Debugger Variable.al|
|Debugger Watch Value.al|
|Drive.al|
|Event Subscription.al|
|Field.al|
|File.al|
|Finish design Save Mode.al|
|Integer.al|
|Key.al|
|License Information.al|
|Monitor.al|
|New Page Pattern.al|
|OLE Control.al|
|Page Metadata.al|
|Page Table Field.al|
|Permission Range.al|
|Printer.al|
|Report Metadata.al|
|Server.al|
|Session.al|
|SID - Account ID.al|
|System Object.al|
|Table Field Types.al|
|Table Information.al|
|Table Metadata.al|
|Table Relations Metadata.al|
|Table Synch. Setup.al|
|Time Zone.al|
|Windows Language.al|

## See Also 
[Differences in the Dynamics NAV Development Environments](devenv-differences.md)  
[Developer Reference](devenv-reference-overview.md)
