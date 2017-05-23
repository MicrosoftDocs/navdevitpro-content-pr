---
title: customer resource type | Microsoft Docs
description: A customer.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ems.date: 02/08/2017
ms.author: solsen
---

# Customer resource type
Represents a customer resource type in Dynamics 365 for Financials.

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET customer](../api/dynamics_get_customer.md)|customer|Get a customer.|
|[CREATE customer](../api/dynamics_create_customer.md)|customer|Create a customer.|
|[UPDATE customer](../api/dynamics_update_customer.md)|customer|Update a customer.|
|[DELETE customer](../api/dynamics_delete_customer.md)|none|Delete a customer.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the item. Read-Only.|
|number|string|The customer number.|
|displayName|string|Specifies the customer's name. This name will appear on all sales documents for the customer.|
|address|[NAV.PostalAddress](../resources/dynamics_complex_types.md)|Specifies the customer's address. This address will appear on all sales documents for the customer.|
|phoneNumber|string|Specifies the customer's telephone number.|
|email|string|Specifies the customer's email address.|
|website|string|Specifies the customer's home page address.|
|taxLiable|boolean|Specifies if the customer or vendor is liable for sales tax. Set to **True** if the customer is tax liable.|
|currencyCode|numeric|The default currency code for the customer.|
|paymentTerms|[NAV.PaymentTermsType](../resources/dynamics_complex_types.md)|Specifies a code that indicates the payment terms that you require of the customer.|
|paymentMethod|[NAV.PaymentMethod](../resources/dynamics_complex_types.md)|Specifies how the customer usually submits payment, such as bank transfer or check.|
|shipmentMethod|[NAV.ShipmentMethod](../resources/dynamics_complex_types.md)|Specifies which shipment method to use when you ship items to the customer.|
|blocked|string|Specifies that transactions with the customer cannot be posted. Set to **"All"** if the customer is blocked, set to blank if not blocked.|
|balance|numeric|Specifies the payment amount that the customer owes for completed sales. This value is also known as the customer's balance. Read-Only.|
|lastModifiedDateTime|datetime|The last datetime the customer was modified. Read-Only.|  


## Relationships
A Currency(currencyCode) must exist in the Currencies table.

A Payment Term(paymentTerms) must exist in the Payment Terms table.

A Shipment Method(shipmentMethod) must exist in the Shipment Method table.

A Payment Method(paymentMethod) must exist in the Payment Method table.

## JSON representation

Here is a JSON representation of the resource.


```json
{
    "id": "GUID",
    "number": "string",
    "displayName": "string",
    "address": "NAV.PostalAddress",
    "phoneNumber": "string",
    "email": "string",
    "website": "string",
    "taxLiable": "boolean",
    "currencyCode": "string",
    "paymentTerms": "NAV.PaymentTermsType",
    "shipmentMethod": "NAV.ShipmentMethod",
    "paymentMethod":  "NAV.PaymentMethod",
    "blocked": "string",
    "balance": "decimal",
    "lastModifiedDateTime": "datetime"
}


```
## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 
