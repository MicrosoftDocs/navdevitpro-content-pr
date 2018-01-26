---
title: "AL Formatter"
description: "Document the AL Formatter."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 11/06/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: solsen
caps.latest.revision: 18
---

[!INCLUDE[newdev_dev_preview](includes/newdev_dev_preview.md)]

> [!NOTE]  
> [!INCLUDE[nav_not_supported](includes/nav_not_supported.md)]

# AL Formatter
The AL Language extension offers users the option to automatically format their source code. This capability increases the usability of the editor by allowing developers to instantly fix the indentation and formatting of their code. 

## How to use it
The auto-formatter can be invoked to format an entire AL document or a pre-selected range. In an existing project, open the document that you want to format, right-click inside the document, and select **Format Document**. In the default configuration for Visual Studio Code, the command can be run using the shortcut Alt+Shift+F.

![Format Document](media/format-document.gif)  

To format a range, in an already opened project, open the document that you want to modify, select the specific range to format, right-click, and select **Format Selection**. In the default configuration for Visual Studio Code, the command can be run using the shortcut Ctrl+K, Ctrl+F.


![Format Selection](media/format-selection.gif)

## What does it do
The auto-formatter analyzes the syntax tree of the AL code that you are formatting and, using rules developed based on the coding and style guidelines for AL, inserts and removes whitespace from key points in the document to make it more readable.
The rules used by the auto-formatter cannot be configured by the user. This limitation is present to allow for a uniform style to be used throughout the community of AL developers.

## See Also
[Differences in the Dynamics NAV Development Environments](devenv-differences.md)  
[AL Development Environment](devenv-reference-overview.md)  
