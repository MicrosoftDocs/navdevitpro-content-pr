---
title: customers resource type | Microsoft Docs
description: Represents a customer in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/01/2020
ms.author: solsen
---

# customers resource type
Represents a customer in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method          |Return Type| Description      |
|:----------------|:----------|:-----------------|
|[GET customers](../api/dynamics_customer_get.md)      |customers   |Gets a customer.   |
|[POST customers](../api/dynamics_create_customer.md)|customers   |Creates a customer.|
|[PATCH customers](../api/dynamics_customer_update.md)|customers   |Updates a customer.|
|[DELETE customers](../api/dynamics_customer_delete.md)|none        |Deletes a customer.|



## Navigation 

| Navigation    |Return Type| Description      |
|:----------|:----------|:-----------------|
|[agedAccountsReceivable](../resources/dynamics_agedAccountsReceivables.md)|agedAccountsReceivable   |Gets the agedAccountsReceivable of customer. |
|[countryRegion](../resources/dynamics_countryRegion.md)|countryRegion   |Gets the countryRegion of customer. |
|[customerFinancialDetail](../resources/dynamics_customerfinancialdetails.md)|customerFinancialDetail   |Gets the customerFinancialDetails of customer. |
|[currency](../resources/dynamics_currencies.md)|currency   |Gets the currency of customer. |
|[defaultDimensions](../resources/dynamics_defaultDimension.md)|defaultDimension   |Gets the defaultDimension of customer. |
|[paymentMethod](../resources/dynamics_paymentmethods.md)|paymentMethod   |Gets the paymentMethod of customer. |
|[paymentTerm](../resources/dynamics_paymentTerms.md)|paymentTerm   |Gets the paymentTerm of customer. |
|[picture](../resources/dynamics_picture.md)|picture   |Gets the picture of customer. |
|[shipmentMethod](../resources/dynamics_shipmentmethods.md)|shipmentMethod   |Gets the shipmentMethod of customer. |

## Properties

| Property    | Type     |Description|
|:------------|:---------|:----------|
|id           |GUID      |The unique ID of the item. Non-editable.|
|number       |string    |The customer number.|
|displayName  |string    |Specifies the customer's name. This name will appear on all sales documents for the customer.|
|type         |[NAV.contactType](../resources/dynamics_complextypes.md)   |Specifies the type of customer, can be "Company" or "Person".|
|addressLine1 |string    |Specifies the customer's address. This address will appear on all sales documents for the customer.|
|addressLine2 |string    |Specifies the customer's address. This address will appear on all sales documents for the customer.|
|city         |string    |Specifies the customer's city.|
|state        |string    |Specifies the customer's state.|
|postalCode   |string    |Specifies the customer's postal code.|
|phoneNumber  |string    |Specifies the customer's telephone number.|
|email        |string    |Specifies the customer's email address.|
|website      |string    |Specifies the customer's home page address.|
|taxLiable    |boolean   |Specifies if the customer or vendor is liable for sales tax. Set to **true** if the customer is tax liable.|
|taxAreaId    |GUID      |Specifies which tax area the customer belongs to.|
|taxAreaDisplayName|string|Specified the display name of the tax area the customer belongs to.|
|taxRegistrationNumber|string, maximum size 20|Specified the tax registration number of the customer.|
|currencyId   |GUID      |Specifies which currency the customer uses.|
|currencyCode |string   |The default currency code for the customer.|
|paymentTermsId|GUID     |Specifies which payment term the customer uses.|
|paymentMethodId|GUID    |Specifies which payment method the customer uses.|
|shipmentMethodId|GUID   |Specifies which shipment method the customer uses.|
|blocked      |string    |Specifies that transactions with the customer cannot be posted. Set to **All**, if the customer is blocked, set to blank if not blocked.|
|lastModifiedDateTime|datetime|The last datetime the customer was modified. Read-Only.|  

## JSON representation

Here is a JSON representation of the resource.


```json
{
    "id": "GUID",
    "number": "string",
    "displayName": "string",
    "type": NAV.contactType,
    "addressLine1": "string",
    "addressLine2": "string",
    "city": "string",
    "state": "string",
    "postalCode": "string",
    "phoneNumber": "string",
    "email": "string",
    "website": "string",
    "taxLiable": "boolean",
    "taxAreaId": "GUID",
    "taxAreaDisplayName": "string",
    "taxRegistrationNumber": "string",
    "currencyId": "string",
    "currencyCode": "string",
    "paymentTermsId": "GUID",
    "shipmentMethodId": "GUID",
    "paymentMethodId":  "GUID",
    "blocked": "string",
    "balance": "decimal",
    "lastModifiedDateTime": "datetime"
}
```
## See also
  
[Get Customers](../api/dynamics_customer_get.md)  
[Post Customers](../api/dynamics_create_customer.md)  
[Patch Customers](../api/dynamics_customer_update.md)  
[Delete Customers](../api/dynamics_customer_delete.md)  
