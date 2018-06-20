---
title: userGroup resource type | Microsoft Docs
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

# userGroupMember resource type

Represents a userGroup resource type in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md).

## Methods

| Method         | Return Type  |Description|
|:---------------|:-------------|:----------|
|[GET userGroups](../api/microsoft/automation/dynamics_user_get.md)|userGroup|Gets all userGroups|


## Properties

| Property | Type |Description                             |
|:----------------|:-----|:---------------------------------------|
|code               |string  |code of the userGroup.|
|displayName      |string|Display of the useGroup.     |
|defaultProfileID|string|Id of the defaultProfile.|
|assignToAllNewUsers|boolean|If true, all new users are assigned to userGroup|

## Relationships / Navigtion properties

None

## JSON representation

Here is a JSON representation of the extension.

```json
{
    "code": "D365 ADMINISTRATOR",
    "displayName": "Opret og opsæt virksomheder",
    "defaultProfileID": "VIRKSOMHEDSLEDER",
    "assignToAllNewUsers": false
}

```
## EDM metadata

```xml
<EntityType Name="userGroupMember">
                <Key>
                    <PropertyRef Name="code" />
                    <PropertyRef Name="userSecurityID" />
                    <PropertyRef Name="companyName" />
                </Key>
                <Property Name="code" Type="Edm.String" Nullable="false" MaxLength="20" />
                <Property Name="userSecurityID" Type="Edm.Guid" Nullable="false" />
                <Property Name="companyName" Type="Edm.String" Nullable="false" MaxLength="30" />
                <Property Name="displayName" Type="Edm.String" MaxLength="50" />
                <NavigationProperty Name="userGroup" Type="Microsoft.NAV.userGroup" ContainsTarget="true" />
                <NavigationProperty Name="user" Type="Microsoft.NAV.user" ContainsTarget="true" />
                <NavigationProperty Name="automationCompany" Type="Microsoft.NAV.automationCompany" ContainsTarget="true" />
            </EntityType>

```

## See Also

[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
