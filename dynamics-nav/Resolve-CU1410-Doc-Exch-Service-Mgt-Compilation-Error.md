---
title: "Resolving Codeunit 1410 Doc. Exch. Service Mgt. Error When Converting a Database"
description: This article describes how to use the development environment to change the DotNet data type variables.
ms.custom: na
ms.date: 05/12/2021
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 6ea75b39-cf7d-4c88-868b-86fa0be2426b
caps.latest.revision: 4
author: jswymer
---

# Resolving Codeunit 1410 Doc. Exch. Service Mgt. Error When Converting a Database
Use the [!INCLUDE[nav_dev_short_md](includes/nav_dev_short_md.md)] to change the **DotNet** data type variables of the local function **Initialize** to the use Microsoft.Dynamics.Nav.OAuth version 10.0.0.0 assembly (for Dynamics NAV 2017) or version 11.0.0.0 (for Dynamics NAV 2018), as shown in the following table for Dynamics NAV 2018.

|  Variable  |  DatType  |  Subtype  |
|------------|-----------|-----------|
|OAuthAuthorization|DotNet|Microsoft.Dynamics.Nav.OAuthHelper.OAuthAuthorization.'Microsoft.Dynamics.Nav.OAuth, Version=11.0.0.0'|
|OAuthConsumer|DotNet|Microsoft.Dynamics.Nav.OAuthHelper.Consumer.'Microsoft.Dynamics.Nav.OAuth, Version=11.0.0.0'|
|OAuthToken|DotNet|Microsoft.Dynamics.Nav.OAuthHelper.Token.'Microsoft.Dynamics.Nav.OAuth, Version=11.0.0.0'|

 [Converting a Database](Converting-a-Database.md)  
 [Resolving Compilation Errors When Converting a Dynamics NAV 2016 Database](Resolve-Compile-Errors-When-Converting-Dynamics-NAV-2016-Database.md)  
