---
title: companies resource type | Microsoft Docs
description: A company in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/01/2019
ms.author: solsen
---

# companies resource type
Represents a companies resource type in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)]. 

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Microsoft Dynamics NAV](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method         | Return Type  |Description|
|:---------------|:-------------|:----------|
|[GET companies](../api/dynamics_companies_get.md)|companies|Get a company.|

## Properties

| Property        | Type |Description                             |
|:----------------|:-----|:---------------------------------------|
|id               |GUID  |The unique ID of the company. Read-Only.|
|name             |string|Specifies the Company.                  |
|displayName      |string|Specifies the company display name.     |
|systemVersion    |string|Specifies the internal version of the company.|
|businessProfileId|string|Specifies the Business Profile ID linked to the company.|


## Relationships
None

## JSON representation

Here is a JSON representation of the company.

```json
{
  "id": "GUID",
  "name": "string",
  "displayName": "string",
  "systemVersion": "string",
  "businessProfileId": "string"
}
```

## See Also
  
[Get Companies](../api/dynamics_companies_get.md)  
[Company Information](dynamics_companyinformation.md)  
[Get Company Information](../api/dynamics_companyinformation_get.md)  
[Update Company Information](../api/dynamics_companyinformation_update.md)  
