---
title: "Developing for Dynamics 365 for Financials Overview"
description: "Overview of the new development experience."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 11/02/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.author: solsen
ms.assetID: be636361-9de8-4efb-ad50-445e4b7b3255
---

# Developing for Dynamics 365 for Financials Overview
Developing for [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] is done by creating an extension to a [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] solution. Extensions are a programming model where functionality is defined as an addition to existing objects and defines how they are different or modify the behaviour of the solution. 
You might already be familiar with the extension model working with [!INCLUDE[navnow_md](includes/navnow_md.md)]. For more information, see [Extending Microsoft Dynamics NAV Using Extension Packages](../dynamics-nav/extending-microsoft-dynamics-nav-using-extension-packages.md).

If you're new to building extensions for [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)], we recommend that you read this document to get an understanding of the basics and terms you will encounter while working. Next, follow the [Getting Started Developing for Dynamics 365 for Financials](dyn-fin-geting-started-dev-env.md) to set up your system and then jump straight into your first extension - Hello World [link to hello world]().

## Understanding Objects in Dynamics 365 for Financials
All functionality in [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] is coded in an object. Table objects define the table schema that holds data, Page objects represent the pages seen in the user interface and codeunits contain code for logical calculations and for the application behavior. These objects are stored as code, known as AL code, and are saved in files with the ```.al``` file extension.  
    
    **Note:** A single .al file may contain multiple objects.      

There are two other special objects which are specifically used for building extensions. Table Extension objects and Page Extension Objects are used for defining additive or overriding changes to Page or Table objects. For example, an extension for managing a business that sells organic food may define a Table Extension object for the Item table that contains an additional field ```Organic``` and ```Produced Locally```. The ```Organic``` and ```Produced Locally``` fields aren't usually present in the Item table, but through the Table Extension these data fields will now be available to store data in and to access from code.

For more information, see [Page Extension Object](dyn-fin-page-ext-object.md) and [Table Extension Objects](dyn-fin-table-ext-object.md).

## Developing Extensions in Visual Studio Code
Using the AL extension for Visual Studio Code, you'll get the benefits of a modern development environment along with seamless publishing and execution integration with your [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] tenant. For more information on getting up and running, see [Getting Started Developing for Dynamics 365 for Financials](../dynamics-nav/dyn-fin-getting-started-dev-env.md).

Visual Studio Code and the AL Extension lets you do the following tasks:

- Create new files for your solution
- Get assistance with creating the appropriate configuration and setting files 
- Use code snippets that provide templates for coding application objects
- Get compiler validation while coding
- Press F5 to publish your changes and see your code running

For more information, see [Visual Studio Code Docs](https://code.visualstudio.com/docs).

## Syntax
The syntax of the AL language is designed to assist in building business applications. The AL language is an evolution from the original programming languge used in [!INCLUDE[navnow_md](includes/navnow_md.md)] and resembles it very closely. The changes from the [!INCLUDE[navnow_md](includes/navnow_md.md)] language and AL can be found in links in this section.

- [Table Object](dyn-fin-table-object.md)
- [Table Extension Object](dyn-fin-table-ext-object.md)
- [Page Object](dyn-fin-page-object.md)
- [Page Extension Object](dyn-fin-page-ext-object.md)
- [Codeunit Object](dyn-fin-codeunit-object.md)

For information about AL language changes, see [Differences from the Dynamics NAV Development Environment](dyn-fin-differences.md)

## Visual designer
The in-client designer works in the client itself allowing design of pages using a drag-and-drop interface. With this preview of the in-client designer, you can:

- Enter and exit design mode
- Move fields around
- Preview design on device (Phone, Tablet previewer)
- Add existing fields (those that exist in the source table)
- Add new fields (for limited types)
- Save as “MyExtension” which is tenant wide in scope


## Compiling and Deploying
Extensions are compiled as .navm package files. 
<!-- The .navm package file can be deployed to the NAV server ()... 
A .navm package contains the various artifacts that deliver the new functionality to the [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] deployment as well as a manifest that specifies the name, publisher, version, and other attributes of the extension. .json file? -->

<!-- (Future: You manage .navm packages with a series of Windows PowerShell cmdlets that are available in the Microsoft Dynamics NAV 2017 Administration Shell. There are also cmdlets available to ISVs and developers in the Microsoft Dynamics NAV 2017 Development Shell that help create packages.) --> 

## See Also
[Getting Started Developing for Dynamics 365 for Financials](../dynamics-nav/dyn-fin-geting-started-dev-env.md)  
[Keyboard Shortcuts](dyn-fin-keyboard-shortcuts.md)  
[Developer Reference](dyn-fin-reference-overview.md)

