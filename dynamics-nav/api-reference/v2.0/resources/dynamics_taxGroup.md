---
title: taxGroup resource type | Microsoft Docs
description: An taxGroup object in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# taxGroup resource type
Represents an taxGroup object in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET taxGroup](../api/dynamics_taxGroup_get.md)|taxGroup|Get taxGroup object.|

## Properties

| Property     | Type   |Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the taxGroup.|
|number|string, maximum size 20|Specifies the number of the G/L taxGroup.|
|displayName|string, maximum size 50|Specifies the name of the G/L taxGroup.|
|category|string, maximum size 20|Specifies the category of the G/L taxGroup.|
|subCategory|string, maximum size 80|Specifies the subcategory of the taxGroup category of the G/L taxGroup.|
|blocked|boolean|Specifies that entries cannot be posted to the G/L taxGroup. **True** indicates taxGroup is blocked and posting is not allowed.|
|lastModifiedDateTime|datetime|The last datetime the taxGroup was modified.|


## JSON representation

Here is a JSON representation of the resource.


```json
{
   "id": "GUID",
   "code": "string",
   "displayName": "string",
   "taxType": "NAV.taxBufferType",
   "lastModifiedDateTime": "datetime"
}
```
## See also
  
[Get Account](../api/dynamics_taxGroup_get.md)  
[Aged Accounts Payable](dynamics_agedtaxGrouppayable.md)  
[Aged Accounts Receivable](dynamics_agedtaxGroupreceivable.md)  
