---
title: user resource type | Microsoft Docs
description: A user in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: henrikwh, SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/19/2018
ms.author: henrikwh, SusanneWindfeldPedersen
---

# user resource type
Represents a user resource type in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)]. 

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md).

## Methods

| Method         | Return Type  |Description|
|:---------------|:-------------|:----------|
|[GET user](../api/microsoft/automation/dynamics_user_get.md)|user|Gets all users.|
|[PATCH user](../api/microsoft/automation/dynamics_user_get.md)|user|Update user properties|

## Properties
| Property	      | Type |Description                             |
|:----------------|:-----|:---------------------------------------|
|userSecurityId               |GUID  |The unique ID of the package. Read-Only.|
|userName             |string|Specifies the extension name.                  |
|displayName      |string|Major version of the extension.     |
|state      |string|Minor version of the extension.     |
|expiryDate|DateTimeOffset|Specifies the installation status.|

## Relationships / Navigtion properties


                <NavigationProperty Name="userGroupMembers" Type="Collection(Microsoft.NAV.userGroupMember)" ContainsTarget="true" />
                <NavigationProperty Name="userPermissions" Type="Collection(Microsoft.NAV.userPermission)" ContainsTarget="true" />

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
[Get extensions](../api/microsoft/automation/dynamics_extension_get.md)  
[Install extension](../api/microsoft/automation/dynamics_extension_post.md)  
[Uninstall extension](../api/microsoft/automation/dynamics_extension_post.md)  
