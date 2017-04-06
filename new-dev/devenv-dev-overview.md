---
title: "Developing Extensions Using the Development Environment"
description: "Overview of the development experience for building extensions."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 04/06/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.author: SusanneWindfeldPedersen
ms.assetID: be636361-9de8-4efb-ad50-445e4b7b3255
---

[!INCLUDE[dyn_fin_dev_preview](../dynamics-nav/includes/newdev_dev_preview.md)]

# Developing Extensions Using the Development Environment

Extensions are a programming model where functionality is defined as an addition to existing objects and defines how they are different or modify the behavior of the solution. This section explains how you can develop extensions using the development environment for [!INCLUDE[navnow_md](includes/navnow_md.md)].

<!--
You might already be familiar with the extension model from working with [!INCLUDE[navnow_md](includes/navnow_md.md)]. For more information, see [Extending Microsoft Dynamics NAV Using Extension Packages](extending-microsoft-dynamics-nav-using-extension-packages.md).
-->

If you're new to building extensions for [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)], we recommend that you read this document to get an understanding of the basics and terms you will encounter while working. Next, follow the [Getting Started](devenv-get-started.md) to set up your system.

## Understanding objects in the Dynamics 365 for Financials development environment
All functionality in [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] is coded in objects. Table objects define the table schema that holds data, page objects represent the pages seen in the user interface and codeunits contain code for logical calculations and for the application behavior. These objects are stored as code, known as AL code, and are saved in files with the ```.al``` file extension.  

> [!NOTE]  
> A single .al file may contain multiple objects.      

There are two other special objects which are specifically used for building extensions. Table extension objects and page extension objects are used for defining additive or overriding changes to table or page objects. For example, an extension for managing a business that sells organic food may define a table extension object for the Item table that contains two additional fields, ```Organic``` and ```Produced Locally```. The ```Organic``` and ```Produced Locally``` fields aren't usually present in the Item table, but through the table extension these data fields will now be available to store data in and to access from code. You can then use the page extension object to display the fields that you added to the table object.

> [!NOTE]  
> Table and page extension objects can have a name with a maximum length of 30 characters.      

For more information, see [Page Extension Object](devenv-page-ext-object.md) and [Table Extension Object](devenv-table-ext-object.md).

## Developing extensions in Visual Studio Code
Using the AL extension for Visual Studio Code, you'll get the benefits of a modern development environment along with seamless publishing and execution integration with your [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] tenant. For more information on getting up and running, see [Getting Started](devenv-get-started.md).

Visual Studio Code and the AL extension lets you do the following tasks:

- Create new files for your solution
- Get assistance with creating the appropriate configuration and setting files
- Use code snippets that provide templates for coding application objects
- Get compiler validation while coding
- Press F5 to publish your changes and see your code running

For more information, see [Visual Studio Code Docs](https://code.visualstudio.com/docs).



The changes from the existing [!INCLUDE[navnow_md](includes/navnow_md.md)] language and AL can be found in these topics:

- [Table Object](devenv-table-object.md)
- [Table Extension Object](devenv-table-ext-object.md)
- [Page Object](devenv-page-object.md)
- [Page Extension Object](devenv-page-ext-object.md)
- [Codeunit Object](devenv-codeunit-object.md)
- [Report Object](devenv-report-object.md)

For information about AL language changes, see [Differences in the Dynamics NAV Development Environments](devenv-differences.md).

## In-client designer
The in-client designer works in the client itself allowing design of pages using a drag-and-drop interface. The in-client designer allows building extensions in the client itself by rearranging fields, adding fields, and previewing the page design. For more information, see [Using the Dynamics NAV In-Client Designer](devenv-inclient-designer.md).

## Compiling and deploying
Extensions are compiled as .navx package files. The .navx package file can be deployed to the [!INCLUDE[nav_server_md](includes/nav_server_md.md)]. A .navx package contains the various artifacts that deliver the new functionality to the [!INCLUDE[navnow_md](includes/navnow_md.md)] deployment as well as a manifest that specifies the name, publisher, version, and other attributes of the extension.

## See Also
[Getting Started](devenv-get-started.md)  
[Keyboard Shortcuts](devenv-keyboard-shortcuts.md)    
[Developer Reference](devenv-reference-overview.md)  
[Extending Microsoft Dynamics NAV Using Extension Packages](extending-microsoft-dynamics-nav-using-extension-packages.md)  
[Development](development.md)
