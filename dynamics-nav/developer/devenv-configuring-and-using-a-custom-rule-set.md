---
title: "How to: Use Code Analysis tools"
description: "Configure and use a custom rule set on an AL project."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 13/02/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: solsen
caps.latest.revision: 18
---


# How to: Use Code Analysis tools
In this walkthrough, you will step through the processes that show how you can use code analysis tools. These have been configured to use a customized rule set on an AL project, and you can select a rule set that corresponds with your current project type. 

## About this walkthrough
This walkthrough illustrates the following tasks:
- Create an AL project.
- Enable Code Analysis.
- Add your own code to the project.
- Create and customize a rule set.
- Run Code Analysis and see how the rule set customization behavior works.

## Prerequisites
- The latest version of Visual Studio Code with the AL Language extension installed.

## Using Rule Sets with Code Analysis
First, create a simple project.

## Create an AL project
Press **Alt + A, Alt + L** to create a new project or on the **View** tab in Visual Studio Code, select **Command Palette**, type **AL: Go!** in the **Search box** and select the **AL: Go!** command.
For more information on how to create an AL project, see [Getting Started with AL](devenv-get-started.md).


## Enable Code Analysis
Set the `al.enableCodeAnalysis` to `true` in your project settings, workspace settings, or user settings to enable the code analysis. <!-- This is the official documentation from VS Code about user and workspace settings -->
For more information about Visual Studio Code settings, see [User and Workspace Settings](https://code.visualstudio.com/docs/getstarted/settings).

At this point, the analyzers packaged with the AL Language extensions will be ran on your project.
Next, add some code to the project that will be used to demonstrate violations of the AA0001 **"There must be exactly one space character on each side of a binary operator such as := + - AND OR =."** code analysis rule. 

## Add your own code to the project
In the Visual Studio Code Explorer, open the `HelloWorld.al` file and replace the existing code with the following:

```
pageextension 50100 CustomerListExt extends "Customer List"
{
    trigger OnOpenPage();
    var
        result: Integer;
    begin        
        // The following line will trigger the warning
        // AA0001 "There must be exactly one space character on each side 
        // of a binary operator such as := + - AND OR =." 
        result := 2+2; 
        Message('2 + 2 = ' + Format(result));
    end;
}
```

On the **View** tab of Visual Studio Code, select the **Problems** option and you will see a warning with the message "There must be exactly one space character on each side of '+'.". In this case, the problem can be fixed by running the AL Formatter command.
For more information on how you can use it, see [AL Formatter](devenv-al-formatter.md).

## Create and customize a rule set
1. On the **File** tab in Visual Studio Code, select **New File**.
2. Save the created file with the name `ruleset.json`.
3. Add the following code to the file:

```
{
    "name": "My Custom Rule Set",
    "analyzerRules": [
        {
            "analyzerId": "Microsoft.Dynamics.Nav.CodeCop",
            "rules": [
                {                    
                    "id": "AA0001",                    
                    "action": "None"
                }
            ]
        }
    ]
}
```
4. Add the path to the rule set file in your project settings by setting `al.ruleSetPath` to the path to the rule set file, relative to the project root.
<!-- This will the the second topic that Alex Toader said it is necessary to have it in our documentation. 
For more information about custom rule sets, see [](). 
-->

## Run Code Analysis and see how the rule set customization behavior works.
The code analysis will run in the background and you will see the warning **"There must be exactly one space character on each side of '+'."** disappear from the **Problems** option in Visual Studio Code.
To trigger a new compilation manually, use the **Ctrl+Shift+B** shortcut to build your project.
For more information about AL keyboard shortcuts, see [Keyboard shortcuts](devenv-keyboard-shortcuts.md).


## Limitations
Changing the contents of the rule set file will not be detected by the AL Language extension. To see the effects of changing the rule set file, you can try any of the following:
- Trigger a new compilation manually by using **Ctrl+Shift+B**.
- Reload the window.
- In the project settings, change the `al.ruleSetPath` setting to an invalid path, save the settings file, and finally change back the setting and save it.


## See also
[Development in AL](devenv-dev-overview.md)  
[Debugging in AL](devenv-debugging.md)
