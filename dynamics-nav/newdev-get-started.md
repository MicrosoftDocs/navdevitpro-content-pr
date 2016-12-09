---
title: "Getting Started"
description: "Description of how to get started with the new development environment"
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 12/06/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: solsen
caps.latest.revision: 18
---

[!INCLUDE[dyn_fin_dev_preview](../dynamics-nav/includes/newdev_dev_preview.md)]

# Getting Started
To get started writing extensions for [!INCLUDE[navnow_md](includes/navnow_md.md)] you will need a [!INCLUDE[navnow_md](includes/navnow_md.md)] tenant, and Visual Studio Code. Visual Studio Code is a cross platform editor that you will use for coding and debugging. For the preview, you will download a VM from the Microsoft Azure Gallery which is set up for trying out the new development environment.

## Steps
1) First, you will need an Azure subscription. You can sign up for a [free subscription](https://azure.microsoft.com/en-us/free/).   
2) Go to [Microsoft Azure Marketplace](https://ms.portal.azure.com/#blade/Microsoft_Azure_Marketplace/GalleryFeaturedMenuItemBlade/selectedMenuItemId/home) and search for **Microsoft Dynamics NAV Developer Preview**.  
3) Follow the instructions to deploy and run.   
4) When you have a virtual machine set up, you will see a Welcome text and here you can choose to try out the developer preview following the instructions on the screen.

# Getting started with Visual Studio Code
With the developer preview, you get sample code that compiles and runs. When you want to start creating your own project, you will need to create a new project to contain it. Visual Studio Code manages projects by including all files from a directory. Whatever files exist in that directory are then part of your project. In addition there are two other configuration files; ```app.json``` and ```launch.json```. You can define these yourself, possibly by copying the files from sample code or you can have the system autogenerate them for you. Building the solution (Ctrl+Shift+B) will create the ```app.json``` file and publishing (F5) will generate the ```launch.json``` file.
Within these files, you’ll need to set up some parameters to connect to your server. The following table shows these settings.

|File|Setting|Mandatory|Value|
|----|-------|---------|-----|
|||||


## See Also 
[Differences in the Dynamics NAV Development Environments](newdev-differences.md)  
[Developer Reference](newdev-reference-overview.md)
