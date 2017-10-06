---
title: "How to: Create Your First AL Project"
description: "Description of how to get started with the new development environment"
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 10/06/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: solsen
caps.latest.revision: 18
---

[!INCLUDE[newdev_dev_preview](includes/newdev_dev_preview.md)]

# How to: Create Your First AL Project
To get started writing extensions for [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] you will need a [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] tenant, Visual Studio Code, and the AL Language extension. Visual Studio Code is a cross platform editor that you will use for coding and debugging. To read more about getting started with the tools, see [Getting Started](devenv-get-started.md).

## Getting started with a default project
To get quickly get started, let's use the HelloWorld example that comes with the AL Language extension as a starting point. To do that, go through the steps below.

1. Launch your [Dynamics 365 for Financials sandbox](https://aka.ms/GetSandboxForFinancials).
2. Launch Visual Studio Code, and then press **Ctrl+Shift+P** to open the command window.
3. Choose **AL:Go!** and then choose **Cloud**.  
4. Enter the credentials that you signed up with, and then press **Download symbols**.  
    If you are not prompted to download symbols, press **Ctrl+Shift+P** and run **AL: Download symbols**.
5. Now, press **Ctrl+Shift+B** to build, and then **F5** to deploy the HelloWorld project.  
    The HelloWorld extension is now deployed to and run on the page that is specified in the `startupObjectID` setting in the `launch.json` file. For more information, see [JSON Files](devenv-json-files.md).

## Modifying the default project

### Creating a table object

1. First, delete the HelloWorld.al file by right-clicking it and choosing **Delete**.
2. Then, add a new file called **RewardsTable.al**.
3. In the **RewardsTable.al** file, type **ttable** to launch the snippet for tables, which is a template for the table object.  
    The AL Language extension has many built-in snippets. For example, each object type has its own snippet, such as **tpage** for page, **treport** for report, **tcodeunit** for codeunit etc.
4. In the table object, replace `id` with `50101` and name the table **Reward**.
5. Now, create fields, by adding the following lines of code to the **RewardsTable.al** file.  
    ```
    fields
    {
        field(1;"Reward ID";Code[30])
        {
        }
        field(2;Description;Text[250])
        {
            NotBlank = true;
        }
        field(3;"Discount Percentage";Decimal)
        {
            MinValue = 0;
            MaxValue = 100;
            DecimalPlaces = 2;
        }
    }

    keys
    {
        key(PK;"Reward ID")
        {
            Clustered = true;
        }
    }
    ```

### Creating a page object

1. Create a new .al file, called **RewardsCard.al**.
2. Use the **tpage** snippet to fill in the structure of the page object. There are two snippets; in this case choose the **Page of type card** option.
3. 


    




## Installing and publishing an extension
To make your extension available to users, the package must be published to a specific Microsoft Dynamics NAV Server instance. The extension can be installed for one or more tenants. For more information about how to install and publish an extension, see [How to: Publish and Install an Extension V2](devenv-how-publish-and-install-an-extension-v2.md). 

## See Also
[Differences in the Dynamics NAV Development Environments](devenv-differences.md)  
[Developer Reference](devenv-reference-overview.md)
