---
title: "JSON Files"
description: "Description of the content of the JSON files."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 08/31/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: solsen
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
|brief|No, but required for AppSource submission|Short description of the extension.|
|description|No, but required for AppSource submission|Longer description of the extension.|
|version|Yes|The version of the app package.|
|privacyStatement|No, but required for AppSource submission|URL to the privacy statement for the extension.|
|EULA|No, but required for AppSource submission|URL to the license terms for the extension.|
|help|No, but required for AppSource submission|URL to the help for the extension.|
|url|No|URL of the extension package.|
|logo|No, but required for AppSource submission|URL to the logo for the extension package.|
|dependencies|No|List of dependencies for the extension package.|
|screenshots|No|Relative paths to any screenshots that should be in the extension package.|
|platform|Yes, if system tables are referenced in the extension|The minimum supported version of the platform symbol package file, for example: "11.0.0.0". See the [Symbols](devenv-symbols.md) for the list of object symbols contained in the platform symbol package file.|
|application|Yes, if base application objects are extended or referenced |The minimum supported version and locale of the base application to extend, for example: ```{  "version": "11.0.0.0",  "locale": "W1"  }```|
|idRange|No|An optional range for application object IDs. For all objects outside the range, a compilation error will be raised.|

## Launch.json file

The following table describes the settings in the ```launch.json``` file. The `launch.json` file has two configurations depending on whether the extension is published to a local server or to the cloud.

### Publish to local server settings
|Setting|Mandatory|Value|
|-------|---------|-----|
|name|Yes|"Publish to your own server"|
|type|Yes|Must be set to ".al". Required by Visual Studio Code.|
|request|Yes|Request type of the configuration. Must be set to `launch`. Required by Visual Studio Code.|
|server|Yes|The HTTP URL of your server, for example: `"http://localhost|serverInstance"`|
|serverInstance|Yes|The instance name of your server, for example: `"NAV"`|
|authentication|Yes|Specifies the server authentication method.|
|startupObjectId|Yes|Specifies the ID of the object to open after publishing. Only objects of type Page are currently supported.|

### Publish to cloud settings
|Setting|Mandatory|Value|
|-------|---------|-----|
|name|Yes|"Publish to Microsoft cloud sandbox"|
|type|Yes|Must be set to ".al". Required by Visual Studio Code.|
|request|Yes|Request type of the configuration. Must be set to `launch`. Required by Visual Studio Code.|
|startupObjectId|Yes|Specifies the ID of the object to open after publishing. Only objects of type Page are currently supported.|
|serverInstance|Yes|The instance name of your server, for example: `"US"`|

## The platform symbol file
The platform symbol file contains all of the base app objects that your extension builds on. If the symbol file is not present, you will be prompted to download it. For more information about the platform symbol file, see [Symbols](devenv-symbols.md).

## See Also
[Differences in the Dynamics NAV Development Environments](devenv-differences.md)  
[Developer Reference](devenv-reference-overview.md)
