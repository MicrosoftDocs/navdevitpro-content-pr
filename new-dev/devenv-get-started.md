---
title: "Getting Started"
description: "Description of how to get started with the development environment"
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

# Getting Started
To get started writing extensions for [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] you will need a [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] tenant, and Visual Studio Code. Visual Studio Code is a cross platform editor that you will use for coding and debugging. For the preview, you will download a VM (virtual machine) from the Microsoft Azure Gallery. The VM is set up for trying out the new development environment.

## Steps
1) First, you will need an Azure subscription. You can sign up for a [free subscription](https://azure.microsoft.com/en-us/free/).   
2) Go to [Microsoft Azure Marketplace](https://ms.portal.azure.com/#blade/Microsoft_Azure_Marketplace/GalleryFeaturedMenuItemBlade/selectedMenuItemId/home) and search for **Microsoft Dynamics NAV Developer Preview**.  
3) Follow the instructions to deploy and run.   
4) When you have a virtual machine set up, you will see a welcome text and here you can choose to try out the developer preview following the instructions on the screen.

# Getting started with Visual Studio Code
With the developer preview, you get sample code that compiles and runs by following a few steps.  

1) In Visual Studio Code, press **Ctrl**+**Shift**+**P** to show all commands.  
2) Type **AL: Go** (case-insensitive) and select a project folder.  
3) Next, you must choose between a local server or a cloud server.

You now have a HelloWorld sample that compiles and runs. The JSON files in the project are automatically updated with the settings that allows you to press **F5** to build and deploy the solution.

> [!NOTE] If symbols are missing, you will be prompted to download them.

## App.json and launch.json file settings
The JSON files are automatically created when you run the **AL:Go** command. Some of these settings, you may want to change from the default setting. For more information about the JSON files, see [Overview of the JSON Files](devenv-json-files.md).

## The platform symbol file
If platforms symbols are not present, your extension will not compile and you will be prompted to download them. For more information about the platform symbol file, see [Symbol Files](devenv-symbols.md).

## See Also
[Differences in the Dynamics NAV Development Environments](devenv-differences.md)  
[Developer Reference](devenv-reference-overview.md)
