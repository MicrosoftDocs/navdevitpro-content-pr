---
title: permissionSet resource type | Microsoft Docs
description: A permissionSet in Dynamics 365 Business Central.
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

# permissionSet  resource type

Represents a permissionSet resource type in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md).

## Methods

| Method         | Return Type  |Description|
|:---------------|:-------------|:----------|
|[GET permissionSets](../api/dynamics_microsoft_automation_permissionSet_get.md)|permissionSet|Gets permissionSets|


## Properties

| Property | Type |Description                             |
|:----------------|:-----|:---------------------------------------|
|scope               |string  |code of the userGroup.|
|appID      |guid|Display of the useGroup.     |
|id|string|Id of the defaultProfile.|
|displayName|string|If true, all new users are assigned to userGroup|
|extensionName|string|If true, all new users are assigned to userGroup|

## Relationships / Navigation properties

None

## JSON representation

Here is a JSON representation of the permissionSet.

```json
{
    "scope": "System",
    "appID": "00000000-0000-0000-0000-000000000000",
    "id": "D365 ACC. PAYABLE",
    "displayName": "Gæld i Dynamics 365",
    "extensionName": ""
}

```

<!-- 
## EDM metadata

```xml
    <EntityType Name="permissionSet">
        <Key>
            <PropertyRef Name="scope" />
            <PropertyRef Name="appID" />
            <PropertyRef Name="id" />
        </Key>
        <Property Name="scope" Type="Edm.String" Nullable="false" />
        <Property Name="appID" Type="Edm.Guid" Nullable="false" />
        <Property Name="id" Type="Edm.String" Nullable="false" MaxLength="20" />
        <Property Name="displayName" Type="Edm.String" MaxLength="30" />
        <Property Name="extensionName" Type="Edm.String" MaxLength="250" />
    </EntityType>
```
 -->
## See Also

[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
