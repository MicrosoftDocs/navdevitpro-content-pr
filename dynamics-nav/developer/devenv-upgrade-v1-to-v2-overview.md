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
ms.assetID: be636361-9de8-4efb-ad50-445e4b7b3255
---

[!INCLUDE[newdev_dev_preview](includes/newdev_dev_preview.md)]

# Converting Extensions V1 to Extensions V2 Overview
Extensions are a programming model where functionality is defined as an addition to existing objects and defines how they are different or modify the behavior of the solution. This section explains the steps involved in converting Extensions V1; written in C/SIDE to Extensions V2; written using the AL Language extension for Visual Studio Code. The overall steps for the conversion are:

1. Convert the source code from C/AL to the AL syntax.
2. Complete the development of the extension in AL syntax.
3. Write upgrade code that can restore and modify data from the Extension V1 tables.

## Converting the source code
To convert the source code, you must use the Txt2Al conversion tool. The Txt2Al conversion tool allows you to take existing Dynamics NAV objects that have been exported in .txt format and convert them into the new .al format. The .al format is used when developing extensions for [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]. For more information about converting the source code, see [Txt2Al Conversion Tool](devenv-txt2al-tool.md).

<!-- see if Hunter's comments should be applied to the txt2al tool topic -->

## Completing the development of the extension
When the source code has been converted using the Txt2Al conversion tool, open the project folder. For more information about getting started with Visual Studio Code and the AL Language extension, see [Getting Started](devenv-get-started.md). You will probably run into compilation errors, these can typically be due to:

- Object IDs that have changed.  
    The conversion tool tries to convert your code into the object ID range allowed for Extensions V2.
- Field or control names look different; the AL syntax requires names, this means that no empty or default names are allowed.
- Menusuites do not exist in Extensions V2.
- .NET references are not allowed; there is no support for .NET types. Instead you must use the classes that replace .NET calls. For more information, see [Reference](devenv-reference-overview.md).

## Writing upgrade code to move data from Extensions V1
In order to upgrade data from tables in Extensions V1 to Extensions V2, you must write some upgrade code. <!--Refer to the previous section to learn more about the new event based upgrade code in V2.-->

Writing code for the Extensions V1 to Extensions V2 upgrade is very similar to the code that you have been writing for Extensions V1. All of the NAVAPP.* system functions still work with Extensions V2. 

|Example |Description |
|--------|------------|
|`NAVAPP.DeleteArchiveData(70000000)`|Deletes the archived data from table 70000000.|
|`NAVAPP.GetArchiveRecordRef(70000000, archRef)`|Gets a record ref to the archived data from table 70000000.|
|`archVersion := NAVAPP.GetArchiveVersion()`|Gets the version of the archived data from the old extension.|
|`NAVAPP.RestoreArchiveData(70000000)`|Restores the data from the archive of table 70000000.|
 
Using this existing API, you can easily restore/move all of your data from the old V1 extension into the new V2 via an upgrade. 

> [!IMPORTANT]
> Your Extension V1 must be uninstalled before upgrading it to an Extension V2. In order to use `NAVAPP.RestoreArchiveData()`, you must not change the IDs of the tables that are being restored; this means that tables from your Extension V1 must have the same IDs in Extensions V2. 

## See Also
[Getting Started](devenv-get-started.md)  
[Keyboard Shortcuts](devenv-keyboard-shortcuts.md)    
[Developer Reference](devenv-reference-overview.md)  
