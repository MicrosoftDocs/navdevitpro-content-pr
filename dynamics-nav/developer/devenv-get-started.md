---
title: "Getting Started"
description: "Description of how to get started with the new development environment"
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 05/26/2017
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

# Getting Started
To get started writing extensions for [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] you will need a [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] tenant, Visual Studio Code, and the AL Language extension. Visual Studio Code is a cross platform editor that you will use for coding and debugging.

## Steps to set up a sandbox environment and Visual Studio Code
Go through the following steps to set up a sandbox environment. With the preview you get sample code that compiles and runs with just a few commands.

1) Sign up for a [Dynamics 365 for Financials sandbox](https://aka.ms/GetSandboxForFinancials).    
2) Download [Visual Studio Code](https://code.visualstudio.com/Download).  
3) Download the [AL Language extension](https://marketplace.visualstudio.com/items?itemName=ms-dynamics-smb.al).  
4) Press **Alt+A, Alt+L** to trigger the **Go!** command, and then choose **Cloud**.  
5) Enter the credentials you provided for the sign up, and then **Download symbols**.  
6) Press **F5** to deploy and run the extension on your online sandbox tenant.  

> [!NOTE]  
> Use **Ctrl+Shift+P** to clear the credentials cache if you want to deploy against a different environment.

You now have a HelloWorld sample that compiles and runs. The JSON files in the project are automatically updated with the settings that allows you to press **F5** to build and deploy the solution.

> [!NOTE]  
> If symbols are missing, you will be prompted to download them.

As this feature is still in preview you might run into unrecoverable issues from time to time. In these cases, use [Reset Sandbox](https://portal.financials.dynamics.com/reset?env=sandbox&redirectedFromSignup=false) to reset the sandbox and start from a clean environment.

Interested in an on-premise version? It's just as easy. Just sign up by following these steps.

1) First, you will need an Azure subscription, sign up for a free subscription.  
2) Go to the [Developer Preview](http://aka.ms/navdeveloperpreview).  
3) When you have a virtual machine set up, you will see a welcome text and here you can choose to try out the developer preview following the instructions on the screen.  

> [!NOTE]  
> Build and get inspired by our sample library on [GitHub](https://github.com/Microsoft/al).

## JSON file settings
There are two JSON files in the project; the `app.json` file and the `launch.json` file. The files are automatically generated for your project. For more information, see [JSON files](devenv-json-files.md).

## The platform symbol file
The platform symbol file contains all of the base app objects that your extension builds on. If the symbol file is not present, you will be prompted to download it. For more information about the platform symbol file, see [Symbols](devenv-symbols.md).

## Installing and publishing an extension
To make your extension available to users, the package must be published to a specific Microsoft Dynamics NAV Server instance. The extension can be installed for one or more tenants. For more information about how to install and publish an extension, see [How to: Publish and Install an Extension V2](devenv-how-publish-and-install-an-extension-v2.md). 

## See Also
[Differences in the Dynamics NAV Development Environments](devenv-differences.md)  
[Developer Reference](devenv-reference-overview.md)
