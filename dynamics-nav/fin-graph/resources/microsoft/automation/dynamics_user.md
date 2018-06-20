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
The navigational property userGroupMembers links to the users  group membership.
The navigational property userPermissions links to the users permissions.

## JSON representation
Here is a JSON representation of the user.

```json
{
       "userSecurityId": "82ae94d5-3445-47de-8668-714b5113a9c2",
            "userName": "UserName",
            "displayName": "UserName",
            "state": "Enabled",
            "expiryDate": "0001-01-01T00:00:00Z"
}

```

<!-- 
```xml
           <EntityType Name="user">
                <Key>
                    <PropertyRef Name="userSecurityId" />
                </Key>
                <Property Name="userSecurityId" Type="Edm.Guid" Nullable="false" />
                <Property Name="userName" Type="Edm.String" MaxLength="50" />
                <Property Name="displayName" Type="Edm.String" MaxLength="80" />
                <Property Name="state" Type="Edm.String" />
                <Property Name="expiryDate" Type="Edm.DateTimeOffset" />
                <NavigationProperty Name="userGroupMembers" Type="Collection(Microsoft.NAV.userGroupMember)" ContainsTarget="true" />
                <NavigationProperty Name="userPermissions" Type="Collection(Microsoft.NAV.userPermission)" ContainsTarget="true" />
            </EntityType>
```
 -->
## See Also
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[Get extensions](../api/microsoft/automation/dynamics_extension_get.md)  
[Install extension](../api/microsoft/automation/dynamics_extension_post.md)  
[Uninstall extension](../api/microsoft/automation/dynamics_extension_post.md)  
