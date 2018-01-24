---
title: "Runtime packages - cmdlets"
description: "Document the Runtime Packages."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 01/22/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: solsen
caps.latest.revision: 18
---


# Runtime Packages
For distributing extensions, it is possible to generate runtime packages that do not contain AL code, but only the final artifacts used by the server at runtime. 

## How to use it
The first step in using runtime packages is to have an extension developed and published to an on-premise instance.
Next, use the following PowerShell command to connect to the server, find the extension, and download the runtime package.

`Get-NavAppRuntimePackage`

For publishing and installing the package, use the following PowerShell commands: 

`Publish-NavApp`

`Install-NavApp`

### Example 

The following example gets the NAV App runtime package with the provided name and version.

`Get-NAVAppRuntimePackage -ServerInstance DynamicsNAV -AppName 'Proseware SmartApp' -Version 2.3.4.500 -ExtensionPath 'Prosware SmartApp_2.3.4.500_runtime.app'`

## When to use it 

The extensions can be installed on servers that do not have a developer license. The license is checked at the server where the runtime package is generated. 
Runtime packages are used when users want to protect their intellectual property by not shipping their AL source code with the extension. 

### Limitations 

Runtime packages come with the limitation that they only work for on-premise installations and cannot be submitted to AppSource. Moreover, the debugging experience is very limited since no source code is available. 
 


