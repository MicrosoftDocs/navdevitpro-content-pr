---
title: Sales Order resource type | Microsoft Docs
description: A Sales Order.
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

# Sales Order resource type
Represents a salesOrder resource type in [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET Sales Order](get-salesorder.md)|Sales Order|Get a Sales Order object|
|[POST Sales Order](create-salesorder.md)|Sales Order|Create a Sales Order object|
|[PATCH Sales Order](update-salesorder.md)|Sales Order|Update a Sales Order object|
|[DELETE Sales Order](delete-salesorder.md)|none|Delete a Sales Order object|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The order ID. Read-Only.|
|number|string|The order number. Read-Only.|
|orderDate|date|The order date|
|customerId|GUID|The id of the order customer.|
|contactId|GUID|The exchange contact id for the given customer. If a customer id is not specified, we will use the contact id to find it.|
|customerNumber|string|The customer number for the order.|
|customerName|string|The full name of the customer. Read-Only.|
|billingPostalAddress|complex|The billing postal address for the order.|  
|currencyCode|string|The currency code for the order.|
|pricesIncludeTax|boolean|Specifies whether the prices include Tax or not. Read-Only.|
|paymentTerms|string|The payment terms of the order.|
|salesperson|string|The salesperson code for the order.|
|partialShipping|boolean|Specifies whether partial shipping of items is preferred or not.|
|requestedDeliveryDate|Date|The requested delivery date.|
|discountAmount|numeric|The order discount amount|
|discountAppliedBeforeTax|boolean|Specifies whether the discount is applied before tax.|
|totalAmountExcludingTax|numeric|The total amount excluding tax. Read-Only.|
|totalTaxAmount|numeric|The total tax amount for the order. Read-Only.|
|totalAmountIncludingTax|numeric|The total amount for the order, including tax. Read-Only.|
|fullyShipped|boolean|Specifies whether the items of the order were fully shipped or not.|
|status|string|The order status. Status can be: Cancelled, Paid, On hold, Created. Read-Only.|
|lastModifiedDateTime|datetime|The last datetime the sales order was modified. Read-Only.|


## Relationships
A Currency(currencyCode) must exist in the Currencies table.

A Payment Term(paymentTerms) must exist in the Payment Terms table.

A Shipment Method(shipmentMethod) must exist in the Shipment Method table.

A Customer (customerId) must exist in the Customer table.

## JSON representation

Here is a JSON representation of the resource.


```json
{
      "id": "GUID",
      "number": "String",
      "orderDate": "Date",
      "customerId": "GUID",
      "contactId": "GUID",
      "customerNumber": "String",
      "customerName": "String",
      "billingPostalAddress": {NAV.PostalAddress},
      "currencyCode": "String",
      "pricesIncludeTax": boolean,
      "paymentTerms": "String",
      "salesperson": "String",
      "partialShipping": boolean,
      "requestedDeliveryDate": "Date",
      "discountAmount": decimal,
      "discountAppliedBeforeTax": boolean,
      "totalAmountExcludingTax": decimal,
      "totalTaxAmount": decimal,
      "totalAmountIncludingTax": decimal,
      "fullyShipped": boolean,
      "status": "String",
      "lastModifiedDateTime": "DateTime"
}

```
## See Also
[Graph Reference](graph-reference.md)  
