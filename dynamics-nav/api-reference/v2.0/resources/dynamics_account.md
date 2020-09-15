---
title: account resource type | Microsoft Docs
description: A account object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/15/2020
ms.author: solsen
---

# account resource type
Represents an account in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods
| Method | Return Type|Description |
|:--------------------|:-----------|:-------------------------|
|[GET account](../api/dynamics_account_Get.md)|account|Gets a account object.|






## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|id|GUID|The unique ID of the item. Non-editable.|
|number|string|Specifies the number of the account.|
|displayName|string|Specifies the account's name. This name will appear on all sales documents for the account.|
|category|string|Specifies the category of the account.|
|subCategory|string|Specifies the subcategory of the account category of the G/L account.|
|blocked|boolean|Specifies that entries cannot be posted to the account. **True** indicates account is blocked and posting is not allowed.|
|lastModifiedDateTime|datetime|The last datetime the account was modified. Read-Only.|


## JSON representation

Here is a JSON representation of the account resource.


```json
{
   "id": "GUID",
   "number": "string",
   "displayName": "string",
   "category": "string",
   "subCategory": "string",
   "blocked": "boolean",
   "lastModifiedDateTime": "datetime"
}
```
## See also

[GET account](../api/dynamics_account_Get.md)

