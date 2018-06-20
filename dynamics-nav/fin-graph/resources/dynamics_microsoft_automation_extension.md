---
title: extension resource type | Microsoft Docs
description: A extension in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: henrikwh

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/19/2018
ms.author: solsen
---

# extension resource type

Represents a extension resource type in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)]. 

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md).

## Methods

| Method         | Return Type  |Description|
|:---------------|:-------------|:----------|
|[GET extensions](../api/dynamics_microsoft_automation_extension_get.md)|extension|Gets all published extensions.|

## Bound Actions

| Actions         | Return Type  |Description|
|:---------------|:-------------|:----------|
|[Microsoft.NAV.install](../api/dynamics_microsoft_automation_extension_post.md)|none|Installs an published extension.|
|[Microsoft.NAV.uninstall](../api/dynamics_microsoft_automation_extension_post.md)|none|Uninstalls an extension extensions.|

## Properties

| Property	      | Type |Description                             |
|:----------------|:-----|:---------------------------------------|
|packageId               |GUID  |The unique ID of the package. Read-Only.|
|displayName             |string|Specifies the extension name.                  |
|publisher|string|Specifies the publisher of the extension.                  |
|versionMajor      |int|Major version of the extension.     |
|versionMinor      |int|Minor version of the extension.     |
|isInstalled|boolean|Specifies the installation status.|

## Relationships
None

## JSON representation
Here is a JSON representation of the extension.

```json
{
    "packageId": "bbd8e783-238a-4a72-8071-c0d4ea8884e7",
    "displayName": "Sales and Inventory Forecast",
    "publisher": "Microsoft",
    "versionMajor": 2,
    "versionMinor": 0,
    "isInstalled": true
}

```

## See Also
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
 
