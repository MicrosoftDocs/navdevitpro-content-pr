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
With [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] we introduce a new developer experience that lets you write extensions and customizations in Visual Studio Code without modifying original application objects. Using extensions as the way to modify [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] provides a flexible and upgradeable solution that doesn't change original application objects, but simply just extends them.  VS Code has something for the whole family!
You might already be familiar with the extension model working with... For more information, see [old way of doing things description]().

## Developing Extensions in Visual Studio Code
Having installed Visual Studio Code and the AL(?) extension, you are ready to write your first extension to [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]. For more information on getting up and running, see [Getting Started Developing for Dynamics 365 for Financials](dyn-fin-geting-started-dev-env.md).

The AL(?) extension to Visual Studio Code gives you the object structure providing snippets that you can use when you start creating new .al files. The project structure is flat and each object is a file saved as an .al extension file. Inside each object file you define and declare metadata, fields, triggers, events, and functions. A number of new extension object types are ready for this preview. You will be able to write ```PageExtension``` objects and ```TableExtension``` objects to extend ```Page``` and ```Table``` objects. And you can, of course, also add new objects of the following types:
- Page
- Table
- Codeunit ...

For more information, see []().

## Syntax
Developing extensions using the AL extension in Visual Studio Code lets you use the AL language, which means that there is no ramp-up time required to learn a new coding language. You will notice that the syntax is more strict. There are a couple of optimizations to provide a more consistent developer experience. To assist you the IntelliSense will provide lookup and autocomplete on, for example, core application objects, ...  
Unicode support...
For more information, see []().

## Compiling and Deploying
Extensions are compiled as .navm package files. The .navm package file can be deployed to the NAV server ()... A .navx package contains the various artifacts that deliver the new functionality to the [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] deployment as well as a manifest that specifies the name, publisher, version, and other attributes of the extension. .json file? 

(Future: You manage .navm packages with a series of Windows PowerShell cmdlets that are available in the Microsoft Dynamics NAV 2017 Administration Shell. There are also cmdlets available to ISVs and developers in the Microsoft Dynamics NAV 2017 Development Shell that help create packages.) 

## .NET
 .NET integration?

## Visual Designer
Visual Designer – to work side-by-side with VS Code.


## See Also
[Getting Started Developing for Dynamics 365 for Financials](dyn-fin-geting-started-dev-env.md)  
[Page Extension Object](dyn-fin-page-ext-object.md)  
[Table Extension Object](dyn-fin-table-ext-object.md)  
[Keyboard Shortcuts](dyn-fin-keyboard-shortcuts.md)
