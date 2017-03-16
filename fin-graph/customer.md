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

# customer resource type

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET customer](get-customer.md)|customer|Get a customer object.|
|[CREATE customer](create-customer.md)|customer|Create a customer object.|
|[UPDATE customer](update-customer.md)|customer|Update a customer object.|
|[DELETE customer](delete-customer.md)|none|Delete a customer object.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the item. This is a read-only property.|
|number|string|The customer number.|
|displayName|string|Specifies the customer's name. This name will appear on all sales documents for the customer. You can enter a maximum of 50 characters, both numbers and letters.|
|address|string|Specifies the customer's address. This address will appear on all sales documents for the customer.|
|phoneNumber|numeric|Specifies the customer's telephone number.|
|email|string|Specifies the customer's email address.|
|website|string|Specifies the customer's home page address.|
|taxLiable|boolean|Specifies if the customer or vendor is liable for sales tax. Set to **true** if the customer is tax liable.|
|currencyCode|numeric|The default currency code for the customer.|
|paymentTerms|numeric|Specifies a code that indicates the payment terms that you require of the customer.|
|paymentMethod|numeric|Specifies how the customer usually submits payment, such as bank transfer or check.|
|shipmentMethod|numberic|Specifies which shipment method to use when you ship items to the customer.|
|blocked|boolean|Specifies that transactions with the customer cannot be posted. Set to **true** if the customer is blocked.|
|balance|numeric|Specifies the payment amount that the customer owes for completed sales. This value is also known as the customer's balance.|
|lastModifiedDateTime|datetime|The last datetime the customer was modified. Read-Only.|  


## Relationships
A Currency(currencyCode) must exist in the Currencies table.

A Payment Term(paymentTerms) must exist in the Payment Terms table.

A Shipment Method(shipmentMethod) must exist in the Shipment Method table.

A Payment Method(paymentMethod) must exist in the Payment Method table.

## JSON representation

Here is a JSON representation of the resource.


```
{
    "id": "GUID",
    "number": "string",
    "displayName": "string",
    "address": {NAV.PostalAddress}
    "phoneNumber": "string",
    "email": "string",
    "website": "string",
    "taxLiable": "boolean",
    "currencyCode": "string",
    "paymentTerms": {NAV.PaymentTermsType},
    "shipmentMethod": {NAV.ShipmentMethod},
    "paymentMethod":  {NAV.PaymentMethod},
    "blocked": "boolean",
    "balance": "decimal",
    "lastModifiedDateTime": "datetime"
}


```
## See Also
[Graph Reference](graph-reference.md)  
