---
title: dimensionValues resource type | Microsoft Docs
description: A dimension value in Dynamics 365 for Financials.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/11/2017
ms.author: solsen
---

# dimensionValues resource type
Represents a dimension value in Dynamics 365 for Financials.

## Methods

| Method       | Return Type  |Description                   |
|:-------------|:-------------|:-----------------------------|
|[GET dimensionValues](../api/dynamics_dimensionvalue_get.md)|dimensionValues|Gets a dimension value object.|


## Properties
| Property	         | Type                  |Description                                        |
|:-------------------|:----------------------|:--------------------------------------------------|
|id                  |GUID                   |The unique ID of the item.                         |
|code                |string, maximum size 20|The dimension value code.                          |
|displayName         |string                 |Specifies the dimension value's name. This name will appear where the dimension value is used.|
|lastModifiedDateTime|datetime               |The last datetime the dimension value was modified.|  


## JSON representation

Here is a JSON representation of the resource.


```json
{

    "id": "GUID",
    "code": "string",
    "displayName": "string",
    "lastModifiedDateTime": "datetime"
}
```

## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 
