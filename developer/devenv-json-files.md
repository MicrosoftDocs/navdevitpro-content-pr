---
title: "JSON Files"
description: "Description of the content of the JSON files."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 06/07/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: SusanneWindfeldPedersen
caps.latest.revision: 18
---

[!INCLUDE[newdev_dev_preview](includes/newdev_dev_preview.md)]

# JSON Files

There are two JSON files in the project; the `app.json` file and the `launch.json` file. These files are generated automatically when you start a new project. The `app.json` file contains information about extension that you are building, such as publisher information and specifies the minimum version of base application objects that the extension is built on. The `launch.json` file contains information about the server that the extension launches on.

## App.json file
The following table describes the settings in the ```app.json``` file:

|Setting|Mandatory|Value|
|-------|---------|-----|
|id|Yes|The unique ID of the extension. When app.json file is automatically created, the ID is set to a new GUID value.|
|name|Yes|The unique extension name.|
|publisher|Yes|The name of your publisher, for example: **NAV Partner**, **LLC** |
|application|Yes, if base application objects are extended or referenced |The minimum supported version and locale of the base application to extend, for example: ```{  "version": "10.0.0.0",  "locale": "W1"  }```|
|platform|Yes, if system tables are referenced in the extension|The minimum supported version of the platform symbol package file, for example: "10.0.0.0". See the **List of objects in the platform symbol file section** below for the list of object symbols contained in the platform symbol package file.|
|packageCachePath|Yes, if base application is extended or system tables are referenced| The path to the folder where referenced symbol package files are located. The path could either be absolute or relative to the current extension working directory, for example: "../../resources"|

## Launch.json file

The following table describes the settings in the ```launch.json``` file:

|Setting|Mandatory|Value|
|-------|---------|-----|
|server|Yes, if connecting to an on-premises server|The HTTP URL of your server, for example: http://localhost|
|serverInstance|Yes, if connecting to an on-premises server|The instance name of your server, for example: NAV|
|port|No|The port on which the development endpoint is running on the server, default value: 7049|
|tenant|No|The tenant ID in case the server is configured for multitenancy.|
|windowsAuthentication|No|Specifies whether Windows or Azure authentication should be used for publishing the extension. Currently only Windows authentication is supported.|
|startupObjectId|No|The ID of the startup object to launch when you press F5. Currently only objects of type Page are supported.|


## The platform symbol file
The platform symbol file contains all of the base app objects that your extension builds on. If the symbol file is not present, you will be prompted to download it. For more inforamtion about the platform symbol file, see [Symbols](devenv-symbols.md).

## See Also
[Differences in the Dynamics NAV Development Environments](devenv-differences.md)  
[Developer Reference](devenv-reference-overview.md)
