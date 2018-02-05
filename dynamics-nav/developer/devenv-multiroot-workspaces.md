---
title: "Multiroot support - Prone to change"
description: "Handling solutions that contain multiple projects."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 05/02/2018
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


# Multi root support/Handling solutions that contain multiple projects.:

Visual Studio Code recently introduced the so called multi root workspace support which allows you to organize your work in multiple top level folders. See the details on how to add multiple folders to a workspace in https://code.visualstudio.com/docs/editor/multi-root-workspaces
<!--
You can work with multiple project folders in Visual Studio Code with multi-root workspaces. This can be very helpful when you are working on several related projects at one time. For example, you might have a repository with a product's documentation which you like to keep current when you update the product source code.
1. Adding foldes to your existing workspace: 
The File > Add Folder to Workspace... command brings up an Open Folder dialog to select the new folder.
Once a root folder is added, the Explorer will show the new folder as a root in the File Explorer. You can right click on any of the root folders and use the context menu to add or remove folders.
/
You can use drag and drop to add folders to a workspace. Drag a folder to the File Explorer to add it to the current workspace. You can even select and drag multiple folders.

2. Save workspace as 
When you save your workspace, it will create a .code-workspace file and the file name will be displayed in the File Explorer.

If you want to move your Workspace file to a new location, you can use the File > Save Workspace As... command which will automatically set the correct folder paths relative to the new Workspace file location.

-->


The AL Language extension now also supports the multi-root functionality. This feature-set allows you to work with multiple top level AL folders (roots/projects) within one workspace. Not all roots have to be AL-based - you can mix all kinds of roots/projects together. Each AL project will now have its own configuration values for the following settings:   
- 	`al.packageCachePath`   
- 	`al.enableCodeAnalysis`
 
This allows to create a package cache path relative to each project or use the same absolute path to share the same packages across different projects.


Mail Susanne: 
It’s about enabling the capability of having multiple projects in one – there is also a link to the VS Code docs, please read that too. You should also spin up a project to see if it is working (provided that this is checked into the latest build, not sure). Please consider what we need here, maybe just one new topic on how to work with this, plus I think we have a reference in the getting started topic on creating a project, make sure that statement is up to date as well. 
