---
title: "How to: Handle solutions that contain multiple projects"
description: "How to work with multiple AL folders within one workspace."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 07/02/2018
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


# How to: Handle solutions that contain multiple projects 

Visual Studio Code offers the multi-root workspace feature which enables grouping different project folders into one workspace. The AL Language extension also supports the multi-root functionality and allows you to work with multiple AL folders including roots and projects within one workspace. 
<!--
Sa dau un exemplu aici? 
-->

<!--
Multi-root workspaces let developers group a set of disparate project folders into one workspace, instead of having to work with files and folders residing only in a single root folder. This provides a variety of advantages and use cases, such as working on multiple projects at the same time.
After folders have been added, the workspace can be named and saved and developers can switch back and forth among workspaces through a variety of UI interactions.

search for the official documentation  on VSCode for multi-root.
what does it enable it to do. can you structure your project differently? -->



## Working with multiple project folders 
Go through the following steps to work on several related projects at one time:
1) Add folders to your existing workspace go to **File** tab and select **Add Folder to Workspace**.
2) Save the workspace file by pressing **File** and then **Save Workspace As...** . 
<!-- 3) Reopen the workspace file.
4) Workspace file schema - The schema of .code-workspace is fairly straightforward. You have an array of folders with either absolute or relative paths. Relative paths are better when you want to share Workspace files.

You can override the display name of your folders with the name attribute for a clearer display in the Explorer. 

+ Maybe include this part: 
With multiple root folders in one workspace, it is possible to have a .vscode folder in each root folder defining the settings that should apply for that folder. To avoid setting collisions, only resource (file, folder) settings are applied when using a multi-root workspace. Settings which affect the entire editor (for example, UI layout) are ignored. For example, two projects cannot both set the zoom level.

User settings are supported as with single folder project and you can also set global Workspace settings which will apply to all folders in your multi-root Workspace. Global Workspace settings will be stored in your .code-workspace file.
When you go from a single folder instance to multiples folders, VS Code will add the appropriate editor-wide settings from the first folder to the new global Workspace settings.

You can easily review and modify the different settings files through the Settings editor. The Settings editor dropdown lets you select your User settings, global Workspace settings and individual folder settings.

settings dropdown

You can also open specific settings files with the commands:

Preferences: Open User Settings - Open your global User settings
Preferences: Open Workspace Settings - Open the settings section of your Workspace file.
Preferences: Open Folder Settings - Open the settings for the active folder.
Global Workspace settings override User settings and folder settings can override Workspace or User settings.
-->

You can work with multiple project folders in Visual Studio Code with multi-root workspaces

## Grouping a set of disparate project folders into one workspace

It is not mandatory to use only AL-based roots. Different kinds of projects can be mixed, and each AL project will have its configuration values for the following settings: 
- `al.packageCachePath`  
- `al.enableCodeAnalysis`

The first setting allows you to create a package cache path relative to each project or use the same absolute path to share the same packages across different projects. The second one ...
<!--
Intreaba-l din nou pe Alex ce face al.enableCodeAnalysis
-->


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

<!-- Mail Susanne: 
It’s about enabling the capability of having multiple projects in one – there is also a link to the VS Code docs, please read that too (DONE). You should also spin up a project to see if it is working (provided that this is checked into the latest build, not sure) (DONE). Please consider what we need here, maybe just one new topic on how to work with this, (plus I think we have a reference in the getting started topic on creating a project, make sure that statement is up to date as well. - DONE)  -->
