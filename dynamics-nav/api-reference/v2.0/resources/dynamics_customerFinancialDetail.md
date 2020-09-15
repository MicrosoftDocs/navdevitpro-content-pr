---
title: customerFinancialDetail resource type | Microsoft Docs
description: A customer financial detail object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/15/2020
ms.author: solsen
---

# customerFinancialDetail resource type
Represents an customer financial detail in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method              | Return Type|Description               |
|:--------------------|:-----------|:-------------------------|
|[GET customerFinancialDetail](../api/dynamics_customerFinancialDetail_Get.md)|customerFinancialDetail|Gets a customer financial detail object.|
|[DELETE customerFinancialDetail](../api/dynamics_customerFinancialDetail_Delete.md)|customerFinancialDetail|Deletes a customer financial detail object.|
|[POST customerFinancialDetail](../api/dynamics_customerFinancialDetail_Create.md)|customerFinancialDetail|Creates a customer financial detail object.|
|[PATCH customerFinancialDetail](../api/dynamics_customerFinancialDetail_Update.md)|customerFinancialDetail|Updates a customer financial detail object.|




## Navigation

| Navigation |Return Type| Description |    
|:----------|:----------|:-----------------|
|[customer](../resources/dynamics_customer.md)|customer |Gets the customer of the customerFinancialDetail.|


## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|id|GUID|The unique ID of the item. Non-editable.|
|number|string|Specifies the number of the customer financial detail.|
|balance|decimal|Specifies customer financial detail's total balance.|
|totalSalesExcludingTax|decimal|Total sales exluding tax.|
|overdueAmount|decimal|Overdue amount for the customer financial detail.|


## JSON representation

Here is a JSON representation of the customerFinancialDetail resource.


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

[GET customerFinancialDetail](../api/dynamics_customerFinancialDetail_Get.md)
[DELETE customerFinancialDetail](../api/dynamics_customerFinancialDetail_Delete.md)
[POST customerFinancialDetail](../api/dynamics_customerFinancialDetail_Create.md)
[PATCH customerFinancialDetail](../api/dynamics_customerFinancialDetail_Update.md)
