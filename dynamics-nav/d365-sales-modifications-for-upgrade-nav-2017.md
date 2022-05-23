---
title: "Modifying Dynamics 365 Sales Code for Technical Upgrade to Dynamics NAV 2017"
ms.custom: na
ms.date: 06/30/2021
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.author: jswymer
ms.prod: "dynamics-nav-2018"
author: jswymer
---
# Modifying Dynamics 365 Sales Code for Technical Upgrade to Dynamics NAV 2017

**Applies to:** [!INCLUDE[nav2017](includes/nav2017.md)] cumulative update 55 (July 2021) and later

If your solution integrates with [!INCLUDE[crm](includes/crm_md.md)], and you're upgrading to Dynamics NAV cumulative update 55 (build 30587) or later, you'll have modify some code before you do the upgrade.

## Overview

Dynamics NAV cumulative update 55 introduced the following changes will affect the integration:

- Microsoft .NET Framework 4.6.2 is now required to be installed on the machine where [!INCLUDE[nav2017](includes/nav2017.md)] Server runs. It should install automatically by the [!INCLUDE[nav2017](includes/nav2017.md)] installer (setup.exe). Otherwsie, it can be found on the [!INCLUDE[nav2017](includes/nav2017.md)] installation media (DVD) in the **Prerequisites** folder. You can also downloaded it from [Download .NET Framework 4.6.2](https://dotnet.microsoft.com/en-us/download/dotnet-framework/net462).

- Support for CRM version 8.x has been removed and replaced with CRM SDK version 9.1. The CRM SDK version 9.1 is now part of Dynamics NAV Integration Solution (.zip) found on the installation media (DVD).

- Microsoft.IdentityModel.Clients.ActiveDirectory version 3.19 is required instead of version 2.28.

The following sections explain how to address these changes. 

## Make variable declarations version-agnostic

In C/AL code, you'll have to change the version-specific references to CRM version 8 to be version-agnostic. This section describes the changes that you have to make. The following base application objects objects have been identified as containing such explicit version-specific references, which you'll need to change as a minimum. Your application might contain more.

- Codeunit 5330
- Table 5330

### Variable declaration changes

- Change:

  ```
  DotNet "'Microsoft.Xrm.Sdk, Version=8.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'.<class/type>"  
  ```

  To:

  ```
  DotNet "'Microsoft.Xrm.Sdk'.<class/type>” 
  ```

- Change:

  ```
  DotNet 'Microsoft.Xrm.Tooling.Connector, Version=2.2.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'.<class/type>” 
  ```

  To:

  ``` 
  DotNet "'Microsoft.Xrm.Tooling.Connector'.<class/type>” 
  ```

## Update Microsoft.IdentityModel.Clients.ActiveDirectory (post-upgrade)

Microsoft.IdentityModel.Clients.ActiveDirectory version 3.19 is provided on the installation media (DVD). It should be installed automatically when you install Dynamic NAV Server. But after upgrade, it's a good idea to verify that you have the correct version in the Dynamics NAV Server installation folder. By default, the folder is C:\Program Files\Microsoft Dynamics NAV\100\Service.

To check the version, search the folder for "Microsoft.IdentityModel.Clients.ActiveDirectory.dll". Open its **Properties**, and look at the **File Version** on the **Details** tab. If the version is not 3.19, copy the Microsoft.IdentityModel.Clients.ActiveDirectory.dll file from the **ServiceTier\program files\Microsoft Dynamics NAV\100\Service** folder of the installation media (DVD) to your Dynamics NAV Serve installation folder.
