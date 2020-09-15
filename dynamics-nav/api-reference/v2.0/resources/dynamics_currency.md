---
title: currency resource type | Microsoft Docs
description: A currency object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/15/2020
ms.author: solsen
---

# currency resource type
Represents an currency in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method              | Return Type|Description               |
|:--------------------|:-----------|:-------------------------|
|[GET currency](../api/dynamics_currency_Get.md)|currency|Gets a currency object.|
|[DELETE currency](../api/dynamics_currency_Delete.md)|currency|Deletes a currency object.|
|[POST currency](../api/dynamics_currency_Create.md)|currency|Creates a currency object.|
|[PATCH currency](../api/dynamics_currency_Update.md)|currency|Updates a currency object.|






## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|id|GUID|The unique ID of the item. Non-editable.|
|code|string|The code of the currency.|
|displayName|string|Specifies the currency's name. This name will appear on all sales documents for the currency.|
|symbol|string|Specifies a graphical representation of the unit of measure.|
|amountDecimalPlaces|string|Specifies the number of decimal places the system will display on amounts for this currency.||
|amountRoundingPrecision|decimal|Specifies the size of the interval to be used when rounding amounts for this currency.|
|lastModifiedDateTime|datetime|The last datetime the currency was modified. Read-Only.|


## JSON representation

Here is a JSON representation of the currency resource.


```json
{
   "id": "GUID",
   "code": "string",
   "displayName": "string",
   "symbol": "string",
   "amountDecimalPlaces": "string",
   "amountRoundingPrecision": "decimal",
   "lastModifiedDateTime": "datetime"
}
```
## See also

[GET currency](../api/dynamics_currency_Get.md)
[DELETE currency](../api/dynamics_currency_Delete.md)
[POST currency](../api/dynamics_currency_Create.md)
[PATCH currency](../api/dynamics_currency_Update.md)

