---
title: userGroup resource type | Microsoft Docs
description: A userGroup in Dynamics 365 Business Central.
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

# userGroup resource type

Represents a userGroup resource type in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md).

## Methods

| Method         | Return Type  |Description|
|:---------------|:-------------|:----------|
|[GET userGroups](../api/dynamics_microsoft_automation_usergroup_get.md)|userGroup|Gets all userGroups|



## Properties

| Property | Type |Description                             |
|:----------------|:-----|:---------------------------------------|
|code             |string  |code of the userGroup.|
|displayName      |string  |Display of the useGroup.     |
|defaultProfileID|string   |Id of the defaultProfile.|
|assignToAllNewUsers|boolean|If true, all new users are assigned to userGroup|

## Relationships / Navigation properties

None

## JSON representation

Here is a JSON representation of the userGroup.

```json
{
    "code": "D365 ADMINISTRATOR",
    "displayName": "Opret og opsæt virksomheder",
    "defaultProfileID": "VIRKSOMHEDSLEDER",
    "assignToAllNewUsers": false
}

```

<!-- ## EDM metadata

```xml
    <EntityType Name="userGroup">
                <Key>
                    <PropertyRef Name="code" />
                </Key>
                <Property Name="code" Type="Edm.String" Nullable="false" MaxLength="20" />
                <Property Name="displayName" Type="Edm.String" MaxLength="50" />
                <Property Name="defaultProfileID" Type="Edm.String" MaxLength="30" />
                <Property Name="assignToAllNewUsers" Type="Edm.Boolean" />
    </EntityType>
```
 -->

## See Also
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
