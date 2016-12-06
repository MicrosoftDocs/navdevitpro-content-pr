---
title: "Developing Extensions Using the New Development Environment"
description: "Overview of the new development experience."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 12/06/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.author: solsen
ms.assetID: be636361-9de8-4efb-ad50-445e4b7b3255
---

[!INCLUDE[dyn_fin_dev_preview](../dynamics-nav/includes/newdev_dev_preview.md)]

# Developing Extensions for Dynamics NAV Overview

Developing for [!INCLUDE[navnow_md](includes/navnow_md.md)] is done by creating an extension to a [!INCLUDE[navnow_md](includes/navnow_md.md)] solution. Extensions are a programming model where functionality is defined as an addition to existing objects and defines how they are different or modify the behaviour of the solution.
You might already be familiar with the extension model working with [!INCLUDE[navnow_md](includes/navnow_md.md)]. For more information, see [Extending Microsoft Dynamics NAV Using Extension Packages](extending-microsoft-dynamics-nav-using-extension-packages.md).

> [!NOTE]  
> To get started developing extensions for [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] read more about building them here [Extending Microsoft Dynamics NAV Using Extension Packages](extending-microsoft-dynamics-nav-using-extension-packages.md). For [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)], you have to sign up for [AppSource](https://appsource.microsoft.com/en-us/) and upload your extensions there. For more information, see [Extend Dynamics 365 for Financials](https://madeira.microsoft.com/en-us/documentation/madeira-develop-extensions/). 


If you're new to building extensions for [!INCLUDE[navnow_md](includes/navnow_md.md)], we recommend that you read this document to get an understanding of the basics and terms you will encounter while working. Next, follow the [Getting Started Developing for Dynamics NAV](newdev-get-started.md) to set up your system.
<!-- and then jump straight into your first extension - Hello World [link to hello world]().-->

## Understanding Objects in Dynamics NAV
All functionality in [!INCLUDE[navnow_md](includes/navnow_md.md)] is coded in an object. Table objects define the table schema that holds data, Page objects represent the pages seen in the user interface and codeunits contain code for logical calculations and for the application behavior. These objects are stored as code, known as AL code, and are saved in files with the ```.al``` file extension.  

> [!NOTE]  
> A single .al file may contain multiple objects.      

There are two other special objects which are specifically used for building extensions. Table Extension objects and Page Extension Objects are used for defining additive or overriding changes to Page or Table objects. For example, an extension for managing a business that sells organic food may define a Table Extension object for the Item table that contains an additional field ```Organic``` and ```Produced Locally```. The ```Organic``` and ```Produced Locally``` fields aren't usually present in the Item table, but through the Table Extension these data fields will now be available to store data in and to access from code.

For more information, see [Page Extension Object](newdev-page-ext-object.md) and [Table Extension Objects](newdev-table-ext-object.md).

## Developing Extensions in Visual Studio Code
Using the AL extension for Visual Studio Code, you'll get the benefits of a modern development environment along with seamless publishing and execution integration with your [!INCLUDE[navnow_md](includes/navnow_md.md)] tenant. For more information on getting up and running, see [Getting Started Developing for Dynamics NAV](newdev-get-started.md). 

Visual Studio Code and the AL Extension lets you do the following tasks:

- Create new files for your solution
- Get assistance with creating the appropriate configuration and setting files
- Use code snippets that provide templates for coding application objects 
- Get compiler validation while coding
- Press F5 to publish your changes and see your code running

For more information, see [Visual Studio Code Docs](https://code.visualstudio.com/docs).

## Syntax
The syntax of the AL language is designed to assist in building business applications. The AL language is an evolution from the original programming languge used in [!INCLUDE[navnow_md](includes/navnow_md.md)] and resembles it very closely. From code, you have access to various snippets that will give you a template for a specific object type. 

|Snippet | Object Type |
|--------|-------------|
|```tt```| Table object structure|
|```pp```| Page object structure|
|```cc```| Codeunit object structure|

The changes from the [!INCLUDE[navnow_md](includes/navnow_md.md)] language and AL can be found in links in this section.

- [Table Object](newdev-table-object.md)
- [Table Extension Object](newdev-table-ext-object.md)
- [Page Object](newdev-page-object.md)
- [Page Extension Object](newdev-page-ext-object.md)
- [Codeunit Object](newdev-codeunit-object.md)

For information about AL language changes, see [Differences in the Dynamics NAV Development Environments](newdev-differences.md)

## In-client designer
The in-client designer works in the client itself allowing design of pages using a drag-and-drop interface. The in-client designer allows building extensions in the client itself by rearranging fields, adding existing fields, and previewing the page design. For more information, see [Using the Dynamics NAV In-Client Designer](newdev-inclient-designer.md).

## Compiling and deploying
Extensions are compiled as .navm package files. The .navm package file can be deployed to the [!INCLUDE[nav_server_md](includes/nav_server_md.md)]. A .navm package contains the various artifacts that deliver the new functionality to the [!INCLUDE[navnow_md](includes/navnow_md.md)] deployment as well as a manifest that specifies the name, publisher, version, and other attributes of the extension.

## See Also
[Getting Started](newdev-get-started.md)  
[Keyboard Shortcuts](newdev-keyboard-shortcuts.md)    
[Developer Reference](newdev-reference-overview.md)
[Extending Microsoft Dynamics NAV Using Extension Packages](extending-microsoft-dynamics-nav-using-extension-packages.md)  
[Development](development.md)

