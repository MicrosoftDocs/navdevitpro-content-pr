---
title: "Using the Code Analysis Tools"
description: "Configuring and using a custom rule set on an AL project."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 02/20/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: solsen
caps.latest.revision: 18
---

# Using the Code Analysis Tools
This topic shows how you can use code analysis tools. The code analysis tools are configured to use a customized rule set on an AL project, and you can select a rule set that corresponds with your current project type. 

## Using rule sets with code analysis
First, create a simple project in AL. 
1. Press **Alt + A, Alt + L** to create a new project.
2. Open the Command Palette **Ctrl+Shift+B** and choose either User Settings or Workspace Settings.
3. Copy the setting `al.enableCodeAnalysis` to the settings.json file and set it to `true`: `"al.enableCodeAnalysis": true`.

At this point, the analyzers packaged with the AL Language extensions will be run on your project. Next, add some code to the project that will, in the following example, be used to demonstrate violations of the AA0001 **"There must be exactly one space character on each side of a binary operator such as := + - AND OR =."** code analysis rule. 

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

On the **View** tab of Visual Studio Code, select the **Problems** option and you will see a warning with the message "There must be exactly one space character on each side of '+'.". In this case, the problem can be fixed by running the AL Formatter command. For more information, see [AL Formatter](devenv-al-formatter.md).

## Creating and customizing a rule set
To create and customize a rule set of your own, follow the next steps:

1. On the **File** tab in Visual Studio Code, choose **New File**.
2. Save the empty file with a name, for example `ruleset.json` and make a note of the file path.
3. Add the following code to the `ruleset.json` file:

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
4. In your project settings set `al.ruleSetPath` to the path to the `ruleset.json` file, relative to the project root. For more information about custom rules, see []().

## Running the code analysis
The code analysis will run in the background and you will see the warning **"There must be exactly one space character on each side of '+'."** disappear from the **Problems** option in Visual Studio Code.

To trigger a new compilation manually, use the **Ctrl+Shift+B** shortcut to build your project. For more information about AL keyboard shortcuts, see [Keyboard shortcuts](devenv-keyboard-shortcuts.md).

## Limitations
Changing the contents of the rule set file will not be detected by the AL Language extension. To see the effects of changing the rule set file, you can try any of the following:
- Trigger a new compilation manually by using **Ctrl+Shift+B**.
- Reload the window.
- In the project settings, change the `al.ruleSetPath` setting to a non valid path, save the settings file, and finally change back the setting and save it.

## See also
[Development in AL](devenv-dev-overview.md)  
[Debugging in AL](devenv-debugging.md)
