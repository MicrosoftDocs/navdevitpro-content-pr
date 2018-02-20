---
title: "Choosing Your Dynamics 365 Business Central Development Sandbox Environment"
description: "Overview of the differences between the offered sandbox environments."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 02/07/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.author: solsen
ms.assetID: be636361-9de8-4efb-ad50-445e4b7b3255
---

[!INCLUDE[newdev_dev_preview](includes/newdev_dev_preview.md)]

# Choosing Your Dynamics 365 Business Central Development Sandbox Environment
To get started developing for [!INCLUDE[navnow_md](includes/navnow_md.md)] Tenerife it is important to understand the different options you have at hand. You can either choose to run a sandbox environment deployed as a Dynamics 365 Cloud Service, or you can run a Docker image either hosted as an Azure VM or locally. Both options provide the AL development tools; the Docker sandbox additionally provides access to the C/SIDE development tools.

The following topic outlines the most important capabilities on the offered development sandbox environments for [!INCLUDE[navnow_md](includes/navnow_md.md)] Tenerife. 

|Capability |Sandbox |Docker Container|
|-----------|--------|----------------|
|Deployment |Dynamics 365 Cloud Service managed by Microsoft|Azure VM or on-premises managed by ISV/VAR|
|Production data|Manually uploaded using Rapid Start packages|Manually uploaded using Rapid Start packages|
|Production extensions|Manually installed|Production installed extensions are automatically installed|
|Production services|Manually configured|Not available|
|Cost|Free|Free|
|Development|Designer functionality, such as: </br>Add/Remove components, </br>Move components, </br>Set/clear Freeze pane, </br>Edit captions |Full capabilities of the developer environment|
|Tools|Visual Studio Code, Designer|Visual Studio Code, Designer, familiar tools such as SSMS and C/SIDE.|
|Debugging|Enabled|Enabled|
|Preview design|PC, tablet, and phone|PC|
|Per user customization|Not available|Not available|
|Per tenant customization|Available|Available|
|Database access|No|Yes|
|Creating .app files|Available|Available|
|Testing|SaaS test environment for any .app file. Files will be uploaded into the sandbox using Visual Studio Code.|On-premises test environment|
|Migration test|No|Yes|

## See Also
[Getting Started with AL](devenv-get-started.md)  
[Keyboard Shortcuts](devenv-keyboard-shortcuts.md)    
[AL Development Environment](devenv-reference-overview.md)  
