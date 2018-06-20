---
title: company resource type | Microsoft Docs
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

# company resource type
Represents a user resource type in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)]. 

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md).

## Methods

| Method         | Return Type  |Description|
|:---------------|:-------------|:----------|
|[GET companies](../api/dynamics_microsoft_automation_companies_get.md)|company|Gets all companies.|


## Properties
| Property	      | Type |Description                             |
|:----------------|:-----|:---------------------------------------|
|id               |GUID  |The unique ID of the company. Read-Only.|
|systemVersion             |string|The systemVersion.                  |
|displayName      |string|diplayName of the company.     |
|name      |string|Name of the company.     |
|businessProfileId|string|Id of the businesProfile.|

## Relationships / Navigtion properties
| Navigtion property	      | Type |Description                             |
|:----------------|:-----|:---------------------------------------|
|automationCompanies               | automationCompany|Gets the automationCompanies |
|extensions             |extension|Gets published extensions.                  |
|userGroups      |userGroup|Gets userGroups.     |
|users      |user|Gets the users.     |
|userGroupMembers|userGroupMember|Gets userGroupMembers.|
|userPermissions|userPermission|Gets avaliable userPermissions.|
|permissionSets|permissionSet|Gets avaliable permissionSets.|
|file|file|Gets file containing RapidStart package.|


<!-- ```xml
<NavigationProperty Name="configurationPackages" Type="Collection(Microsoft.NAV.configurationPackage)" ContainsTarget="true" />
                <NavigationProperty Name="file" Type="Collection(Microsoft.NAV.file)" ContainsTarget="true" />
                <NavigationProperty Name="automationCompanies" Type="Collection(Microsoft.NAV.automationCompany)" ContainsTarget="true" />
                <NavigationProperty Name="extensions" Type="Collection(Microsoft.NAV.extension)" ContainsTarget="true" />
                <NavigationProperty Name="userGroups" Type="Collection(Microsoft.NAV.userGroup)" ContainsTarget="true" />
                <NavigationProperty Name="users" Type="Collection(Microsoft.NAV.user)" ContainsTarget="true" />
                <NavigationProperty Name="userGroupMembers" Type="Collection(Microsoft.NAV.userGroupMember)" ContainsTarget="true" />
                <NavigationProperty Name="userPermissions" Type="Collection(Microsoft.NAV.userPermission)" ContainsTarget="true" />
                <NavigationProperty Name="permissionSets" Type="Collection(Microsoft.NAV.permissionSet)" ContainsTarget="true" />
```
 -->

## JSON representation
Here is a JSON representation of the **company**.

```json
{
    "id": "2b8ea70b-1384-448d-b3d7-1d26c41f3cec",
    "systemVersion": "22654",
    "name": "CRONUS Danmark A/S",
    "displayName": "CRONUS Danmark A/S",
    "businessProfileId": ""
}

```

<!-- 
```xml
<EntityType Name="company">
    <Key>
        <PropertyRef Name="id" />
    </Key>
    <Property Name="id" Type="Edm.Guid" Nullable="false" />
    <Property Name="systemVersion" Type="Edm.String" />
    <Property Name="name" Type="Edm.String" MaxLength="30" />
    <Property Name="displayName" Type="Edm.String" MaxLength="250" />
    <Property Name="businessProfileId" Type="Edm.String" MaxLength="250" />
    <NavigationProperty Name="configurationPackages" Type="Collection(Microsoft.NAV.configurationPackage)" ContainsTarget="true" />
    <NavigationProperty Name="file" Type="Collection(Microsoft.NAV.file)" ContainsTarget="true" />
    <NavigationProperty Name="automationCompanies" Type="Collection(Microsoft.NAV.automationCompany)" ContainsTarget="true" />
    <NavigationProperty Name="extensions" Type="Collection(Microsoft.NAV.extension)" ContainsTarget="true" />
    <NavigationProperty Name="userGroups" Type="Collection(Microsoft.NAV.userGroup)" ContainsTarget="true" />
    <NavigationProperty Name="users" Type="Collection(Microsoft.NAV.user)" ContainsTarget="true" />
    <NavigationProperty Name="userGroupMembers" Type="Collection(Microsoft.NAV.userGroupMember)" ContainsTarget="true" />
    <NavigationProperty Name="userPermissions" Type="Collection(Microsoft.NAV.userPermission)" ContainsTarget="true" />
    <NavigationProperty Name="permissionSets" Type="Collection(Microsoft.NAV.permissionSet)" ContainsTarget="true" />
    <Annotation Term="OData.Community.Keys.V1.AlternateKeys">
        <Collection>
            <Record Type="OData.Community.Keys.V1.AlternateKey">
                <PropertyValue Property="Key">
                    <Collection>
                        <Record Type="OData.Community.Keys.V1.PropertyRef">
                            <PropertyValue Property="Alias" String="businessProfileId" />
                            <PropertyValue Property="Name" PropertyPath="businessProfileId" />
                        </Record>
                    </Collection>
                </PropertyValue>
            </Record>
            <Record Type="OData.Community.Keys.V1.AlternateKey">
                <PropertyValue Property="Key">
                    <Collection>
                        <Record Type="OData.Community.Keys.V1.PropertyRef">
                            <PropertyValue Property="Alias" String="name" />
                            <PropertyValue Property="Name" PropertyPath="name" />
                        </Record>
                    </Collection>
                </PropertyValue>
            </Record>
        </Collection>
    </Annotation>
</EntityType>
```
 -->
## See Also
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
 
