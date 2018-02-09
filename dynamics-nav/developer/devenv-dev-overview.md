---
title: "Developing Extensions in AL"
description: "Overview of the development experience for building extensions using the AL language."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 02/01/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.author: solsen
ms.assetID: be636361-9de8-4efb-ad50-445e4b7b3255
---

[!INCLUDE[newdev_dev_preview](includes/newdev_dev_preview.md)]

# Development in AL
Extensions are a programming model where functionality is defined as an addition to existing objects and defines how they are different or modify the behavior of the solution. This section explains how you can develop extensions using the development environment for [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] and [!INCLUDE[navnow_md](includes/navnow_md.md)]. For an overview of developing apps for [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] and [!INCLUDE[navnow_md](includes/navnow_md.md)], see [aka.ms/GetStartedWithApps](devenv-develop-apps-for-fin.md). 

If you're new to building extensions, we recommend that you read this document to get an understanding of the basics and terms you will encounter while working. Next, follow the [Getting Started with AL](devenv-get-started.md) to set up the tools.

> [!NOTE]  
> [!INCLUDE[d365fin_navnow_supported_md](includes/d365fin_navnow_supported_md.md)]

## Understanding objects in the development environment
All functionality in [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] and [!INCLUDE[navnow_md](includes/navnow_md.md)] is coded in objects. The extension model is object-based; you create new objects, and extend existing objects depending on what you want your extension to do. Table objects define the table schema that holds data, page objects represent the pages seen in the user interface and codeunits contain code for logical calculations and for the application behavior. These objects are stored as code, known as AL code, and are saved in files with the ```.al``` file extension.  

> [!NOTE]  
> A single .al file may contain multiple objects.      

There are two other special objects which are specifically used for building extensions. Table extension objects and page extension objects are used for defining additive or overriding changes to table or page objects. For example, an extension for managing a business that sells organic food may define a table extension object for the Item table that contains two additional fields, ```Organic``` and ```Produced Locally```. The ```Organic``` and ```Produced Locally``` fields aren't usually present in the Item table, but through the table extension these data fields will now be available to store data in and to access from code. You can then use the page extension object to display the fields that you added to the table object.

> [!NOTE]  
> Extension objects can have a name with a maximum length of 30 characters.

You have several options for creating new objects with the AL Language extension for Visual Studio Code. For more information about the objects that you can create for your extension, see [AL Development Environment](devenv-reference-overview.md).

## Developing extensions in Visual Studio Code
Using the AL Language extension for Visual Studio Code, you'll get the benefits of a modern development environment along with seamless publishing and execution integration with your [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] tenant. For more information on getting up and running, see [Getting Started with AL](devenv-get-started.md).

Visual Studio Code and the AL Language extension lets you do the following tasks:

- Create new files for your solution
- Get assistance with creating the appropriate configuration and setting files
- Use code snippets that provide templates for coding application objects
- Get compiler validation while coding
- Press F5 to publish your changes and see your code running

For more information, see [Visual Studio Code Docs](https://code.visualstudio.com/docs).

> [!TIP]
> If you have previous experience working with the C/SIDE development environment and need an overview of some of the changes between the two development environments, see [Differences in the Development Environments](devenv-differences.md).

## Designer
The Designer works in the client itself allowing design of pages using a drag-and-drop interface. The Designer allows building extensions in the client itself by rearranging fields, adding fields, and previewing the page design. For more information, see [Using Designer](devenv-inclient-designer.md).

## Compiling and deploying
Extensions are compiled as .app package files. The .app package file can be deployed to the [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] server. An .app package contains the various artifacts that deliver the new functionality to the [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] deployment as well as a manifest that specifies the name, publisher, version, and other attributes of the extension. For information about the manifest, see [JSON Files](devenv-json-files.md).

## Submitting your app
When all development and testing is done, you can submit your extension package to AppSource. Before you submit the extension package, we encourage you to read the checklist to help facilitating the validation. For more information, see [Checklist for Submitting Your App](devenv-checklist-submission.md).

## See Also
[Getting Started with AL](devenv-get-started.md)  
[Keyboard Shortcuts](devenv-keyboard-shortcuts.md)    
[AL Development Environment](devenv-reference-overview.md)  
[FAQ for Developing in AL](devenv-dev-faq.md)  
