---
title: IRS 1099 Code resource type | Microsoft Docs
description: A IRS 1099 Code object.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/08/2017
ms.author: solsen
---

# IRS 1099 code resource type
Represents a irs1099Codes resource type in Dynamics 365 for Financials.

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET irs1099Codes](../api/dynamics_get_irs1099.md)|irs1099Codes|Get a Payment Terms.|
|[POST irs1099Codes](../api/dynamics_create_irs1099.md)|irs1099Codes|Create a Payment Terms.|
|[PATCH irs1099Codes](../api/dynamics_update_irs1099.md)|irs1099Codes|Update a Payment Terms.|
|[DELETE irs1099Codes](../api/dynamics_delete_irs1099.md)|none|Delete a Payment Terms.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the IRS 1099 Code. Read-Only.|
|code|string|Specifies the IRS 1099 Code. |
|displayName|string|Specifies the IRS 1099 Code display name.|
|minimumReportable|decimal|Specifies the minimum value for this box that must be reported to the IRS on a 1099 form.|
|lastModifiedDateTime|datetime|The last datetime the IRS 1099 Code was modified. Read-Only.|  


## Relationships
None

## JSON representation

Here is a JSON representation of the irs1099Codes.


```json
{
  "id": "GUID",
  "code": "string",
  "displayName": "string",
  "minimumReportable": "decimal",
  "lastModifiedDateTime": "datetime"
}

```

## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 
