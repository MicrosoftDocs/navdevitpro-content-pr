---
title: entityMetadata resource type | Microsoft Docs
description: An entityMetadata object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/08/2020
ms.author: solsen
---

# entityMetadata resource type
Represents an entity metadata in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method                                              | Return Type|Description               |
|:----------------------------------------------------|:-----------|:-------------------------|
<!--methods-->

<!--bound-->


## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|entityName|string|nan|
|entitySetName|string|nan|
|entityCaptions|NAV.entityMetadataLabel|nan|
|entitySetCaptions|NAV.entityMetadataLabel|nan|
|properties|NAV.entityMetadataField|nan|
|actions|NAV.entityMetadataAction|nan|
|enumMembers|NAV.entityMetadataEnumMember|nan|


## JSON representation

Here is a JSON representation of the entityMetadata resource.


```json
{
   "entityName": "string",
   "entitySetName": "string",
   "entityCaptions": "NAV.entityMetadataLabel",
   "entitySetCaptions": "NAV.entityMetadataLabel",
   "properties": "NAV.entityMetadataField",
   "actions": "NAV.entityMetadataAction",
   "enumMembers": "NAV.entityMetadataEnumMember",
}
```
## See also

<!--links-->
