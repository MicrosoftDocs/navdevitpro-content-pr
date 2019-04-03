---
title: customerFinancialDetails resource type | Microsoft Docs
description: An customerFinancialDetails entity in Dynamics 365 Business Central.
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

# customerFinancialDetails resource type
Represents an customerFinancialDetails object in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Microsoft Dynamics NAV](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET customerFinancialDetails](../api/dynamics_customerFinancialDetails_get.md)|accounts|Get customerFinancialDetails object.|

## Properties

| Property     | Type   |Description|
|:---------------|:--------|:----------|
|id|GUID|Id of the customerFinancialDetails.|
|number|string|Reference to the customer number.|
|balance|decimal,read-only|Balance for the customer.|
|totalSalesExcludingTax|decimal, read-only|Total sales exluding tax.|
|overdueAmount|decimal, read-only|Overdue amount for the customer.|
|lastModifiedDateTime|datetime|The last datetime the entity was modified.|

## Relationships

None

## JSON representation

Here is a JSON representation of the resource.

```json
{
    "id": "GUID",
    "number": "string",
    "balance": "decimal",
    "totalSalesExcludingTax": "decimal",
    "overdueAmount": "decimal"
}
```
## See also
[Get customerFinancialDetails](../api/dynamics_customerFinancialDetails_get.md)  
