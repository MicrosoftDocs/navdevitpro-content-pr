---
title: automationCompany resource type | Microsoft Docs
description: A automationCompany in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: henrikwh

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/19/2018
ms.author: henrikwh
---

# automationCompany resource type

Represents a automationCompany resource type in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)]. 

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md).

## Methods

| Method         | Return Type  |Description|
|:---------------|:-------------|:----------|
|[GET automationCompanies](../api/microsoft/automation/dynamics_automationCompanies_get.md)|companies|Gets all automationCompanies.|
|[POST automationCompanies](../api/microsoft/automation/dynamics_automationCompanies_post.md)|companies|Creates a company. automationCompanies.|
|[DELETE automationCompanies](../api/microsoft/automation/dynamics_automationCompanies_delete.md)|companies|Deletes a company. automationCompanies.|
|[PATCH automationCompanies](../api/microsoft/automation/dynamics_automationCompanies_patch.md)|companies|Updates a company, automationCompanies.|


## Properties

| Property	      | Type |Description                             |
|:----------------|:-----|:---------------------------------------|
|id               |GUID  |The unique ID of the company. Read-Only.|
|name             |string|Specifies the Company.                  |
|evaluationCompany|string|Specifies the Company is an evaluation company.                  |
|displayName      |string|Specifies the company display name.     |
|businessProfileId|string|Specifies the Business Profile ID linked to the company.|


## Relationships

None

## JSON representation

Here is a JSON representation of the automationCompany.

```json
{
  "id": "GUID",
  "name": "string",
  "evaluationCompany": "boolean",
  "displayName": "string",
  "businessProfileId": "string",
}

```

## See Also
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
