---
title: userGroup resource type | Microsoft Docs
description: A user in Dynamics 365 Business Central.
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

# configurationPackage resource type

Represents a configurationPackage resource type in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md).

## Methods

| Method         | Return Type  |Description|
|:---------------|:-------------|:----------|
|[GET configurationPackages](../api/dynamics_microsoft_automation_configurationpackage_get.md)|configurationPackage|Gets all configurationPackages|
|[POST configurationPackages](../api/dynamics_microsoft_automation_configurationpackage_post.md)|none|Inserts a new configuration package
|[Patch configurationPackages](../api/dynamics_microsoft_automation_configurationpackage_patch.md)|none|Upload a configurationPackage
|[Delete configurationPackages](../api/dynamics_microsoft_automation_configurationpackage_delete.md)|none|Delete a configurationPackage

## Bound Actions

| Actions         | Return Type  |Description|
|:---------------|:-------------|:----------|
|[Microsoft.NAV.import](../api/dynamics_microsoft_automation_configurationpackage_post.md)|none|Imports configurationPackage.|
|[Microsoft.NAV.apply](../api/dynamics_microsoft_automation_configurationpackage_post.md)|none|Applies configuration package.|

## Properties

| Property | Type |Description                             |
|:----------------|:-----|:---------------------------------------|
|code               |string  |code of the configurationPackage.|
|packageName      |string|Name of the configurationPackage.     |
|languageId|int|Id of the language.|
|productVersion|string|Product version.|
|processingOrder|int|Specifies the order of processing.|
|excludeConfigurationTables|boolean|Exclude configuration tables|
|numberOfTables|int|Number of tables|
|numberOfRecords|int|Numbe of records|
|numberOfErrors|int|Number of errros|
|importStatus|string|Status of import|
|applyStatus|string|Status of configurationPackage apply|


## Relationships / Navigation properties

None

## JSON representation

Here is a JSON representation of the extension.

```json
{
    "code": "RAS2",
    "packageName": "SAMPLE",
    "languageId": 0,
    "productVersion": "",
    "processingOrder": 0,
    "excludeConfigurationTables": false,
    "numberOfTables": 12,
    "numberOfRecords": 3,
    "numberOfErrors": 3,
    "importStatus": "Completed",
    "applyStatus": "Completed"
}
```
<!-- 
## EDM metadata

```xml
  <EntityType Name="configurationPackage">
                <Key>
                    <PropertyRef Name="code" />
                </Key>
                <Property Name="code" Type="Edm.String" Nullable="false" MaxLength="20" />
                <Property Name="packageName" Type="Edm.String" MaxLength="50" />
                <Property Name="languageId" Type="Edm.Int32" />
                <Property Name="productVersion" Type="Edm.String" MaxLength="248" />
                <Property Name="processingOrder" Type="Edm.Int32" />
                <Property Name="excludeConfigurationTables" Type="Edm.Boolean" />
                <Property Name="numberOfTables" Type="Edm.Int32" />
                <Property Name="numberOfRecords" Type="Edm.Int32" />
                <Property Name="numberOfErrors" Type="Edm.Int32" />
                <Property Name="importStatus" Type="Edm.String" />
                <Property Name="applyStatus" Type="Edm.String" />
                <NavigationProperty Name="file" Type="Collection(Microsoft.NAV.file)" ContainsTarget="true" />
            </EntityType>
            <Action Name="import" IsBound="true">
                <Parameter Name="bindingParameter" Type="Microsoft.NAV.configurationPackage" />
            </Action>
            <Action Name="apply" IsBound="true">
                <Parameter Name="bindingParameter" Type="Microsoft.NAV.configurationPackage" />
            </Action>

```
 -->
## See Also

[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
