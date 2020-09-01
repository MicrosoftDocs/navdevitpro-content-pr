---
title: customerFinancialDetail resource type | Microsoft Docs
description: Represents a customerFinancialDetail in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# customerFinancialDetail resource type
Represents a customerFinancialDetail in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method          |Return Type| Description      |
|:----------------|:----------|:-----------------|
|[GET customerFinancialDetail](../api/dynamics_customerFinancialDetail_get.md)      |customerFinancialDetail   |Gets a customerFinancialDetail.   |
|[POST customerFinancialDetail](../api/dynamics_create_customerFinancialDetail.md)|customerFinancialDetail   |Creates a customerFinancialDetail.|
|[PATCH customerFinancialDetail](../api/dynamics_customerFinancialDetail_update.md)|customerFinancialDetail   |Updates a customerFinancialDetail.|
|[DELETE customerFinancialDetail](../api/dynamics_customerFinancialDetail_delete.md)|none        |Deletes a customerFinancialDetail.|



## Navigation

| Navigation |Return Type| Description |
|:----------|:----------|:-----------------|
|[customer](../resources/dynamics_customer.md)|customer   |Gets the customer of the customerFinancialDetail.|

## Properties

| Property    | Type     |Description|
|:------------|:---------|:----------|
|id           |GUID      |The unique ID of the item. Non-editable.|
|number       |string    |The customerFinancialDetail number.|
|displayName  |string    |Specifies the customerFinancialDetail's name. This name will appear on all sales documents for the customerFinancialDetail.|
|type         |[NAV.contactType](../resources/dynamics_complextypes.md)   |Specifies the type of customerFinancialDetail, can be "Company" or "Person".|
|addressLine1 |string    |Specifies the customerFinancialDetail's address. This address will appear on all sales documents for the customerFinancialDetail.|
|addressLine2 |string    |Specifies the customerFinancialDetail's address. This address will appear on all sales documents for the customerFinancialDetail.|
|city         |string    |Specifies the customerFinancialDetail's city.|
|state        |string    |Specifies the customerFinancialDetail's state.|
|postalCode   |string    |Specifies the customerFinancialDetail's postal code.|
|phoneNumber  |string    |Specifies the customerFinancialDetail's telephone number.|
|email        |string    |Specifies the customerFinancialDetail's email address.|
|website      |string    |Specifies the customerFinancialDetail's home page address.|
|taxLiable    |boolean   |Specifies if the customerFinancialDetail or vendor is liable for sales tax. Set to **true** if the customerFinancialDetail is tax liable.|
|taxAreaId    |GUID      |Specifies which tax area the customerFinancialDetail belongs to.|
|taxAreaDisplayName|string|Specified the display name of the tax area the customerFinancialDetail belongs to.|
|taxRegistrationNumber|string, maximum size 20|Specified the tax registration number of the customerFinancialDetail.|
|currencyId   |GUID      |Specifies which currency the customerFinancialDetail uses.|
|currencyCode |string   |The default currency code for the customerFinancialDetail.|
|paymentTermsId|GUID     |Specifies which payment term the customerFinancialDetail uses.|
|paymentMethodId|GUID    |Specifies which payment method the customerFinancialDetail uses.|
|shipmentMethodId|GUID   |Specifies which shipment method the customerFinancialDetail uses.|
|blocked      |string    |Specifies that transactions with the customerFinancialDetail cannot be posted. Set to **All**, if the customerFinancialDetail is blocked, set to blank if not blocked.|
|lastModifiedDateTime|datetime|The last datetime the customerFinancialDetail was modified. Read-Only.|  

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
  
[Get Customers](../api/dynamics_customerFinancialDetail_get.md)  
[Post Customers](../api/dynamics_create_customerFinancialDetail.md)  
[Patch Customers](../api/dynamics_customerFinancialDetail_update.md)  
[Delete Customers](../api/dynamics_customerFinancialDetail_delete.md)  
