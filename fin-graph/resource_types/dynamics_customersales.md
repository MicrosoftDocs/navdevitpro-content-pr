---
title: CustomerSales resource type | Microsoft Docs
description: A CustomerSales.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/03/2017
ms.author: solsen
---

# Customer sales statement resource type
Represents an customerSales resource type in Dynamics 365 for Financials.

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET customerSales](../api/dynamics_get_customerSales.md)|CustomerSales|Get a CustomerSales object|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|customerId|GUID|Represents the customer ID.|
|customerNumber|string|Represents the customer number.|
|name|string|Represents the name of the customer .|
|totalSalesAmount|numeric|Represents the customer sales.|
|dateFilter_FilterOnly|date|Represents the date filter for the customer sales.|


## Relationships
None

## JSON representation

Here is a JSON representation of the resource.


```json
{
    "customerId": "GUID",
    "customerNumber": "string",
    "name": "string",
    "totalSalesAmount": "decimal",
    "dateFilter_FilterOnly": "date"
}

```
## See also
[Working with Dynamics 365 for Finance and Operations, Business Edition in Microsoft Graph](dynamics_overview.md)  
