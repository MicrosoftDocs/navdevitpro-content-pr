---
title: salesOrder resource type | Microsoft Docs
description: A sales order object in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# salesOrder resource type
Represents a sales order in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET salesOrder](../api/dynamics_salesorder_get.md)|salesOrder|Get a sales order object.|
|[POST salesOrder](../api/dynamics_create_salesorder.md)|salesOrder|Create a sales order object.|
|[PATCH salesOrder](../api/dynamics_salesorder_update.md)|salesOrder|Update a sales order object.|
|[DELETE salesOrder](../api/dynamics_salesorder_delete.md)|none|Delete a sales order object.|


## Navigation

| Navigation |Return Type| Description |
|:----------|:----------|:-----------------|
|[customer](../resources/dynamics_customer.md)|customer   |Gets the customer of the salesOrder.|
|[countryRegion](../resources/dynamics_countryregion.md)|countryRegion   |Gets the countryregion of the salesOrder.|
|[currency](../resources/dynamics_currency.md)|currency   |Gets the currency of the salesOrder.|
|[paymentTerm](../resources/dynamics_paymentterm.md)|paymentTerm   |Gets the paymentterm of the salesOrder.|
|[shipmentMethod](../resources/dynamics_shipmentmethod.md)|shipmentMethod   |Gets the shipmentmethod of the salesOrder.|
|[salesOrderLines](../resources/dynamics_salesorderlines.md)|salesOrderLines   |Gets the salesorderlines of the salesOrder.|
|[attachments](../resources/dynamics_attachments.md)|attachments   |Gets the attachments of the salesOrder.|
|[dimensionSetLines](../resources/dynamics_dimensionsetlines.md)|dimensionSetLines   |Gets the dimensionsetlines of the salesOrder.|



## Properties

| Property     | Type   |Description|
|:---------------|:--------|:----------|
|id|GUID|The order ID. Non-editable.|
|number|string, maximum size 20|The order number. Read-Only.|
|orderDate|date|The order date|
|customerId|GUID|The id of the order customer.|
|contactId|string, maximum size 250|The exchange contact id for the given customer. If a customer id is not specified, we will use the contact id to find it.|
|customerNumber|string, maximum size 20|The customer number for the order.|
|customerName|string, maximum size 50|The full name of the customer. Read-Only.|
|billingPostalAddress|complex|The billing postal address for the order.|  
|currencyId|GUID|The id of the order currency.|
|currencyCode|string, maximum size 10|The currency code for the order.|
|pricesIncludeTax|boolean|Specifies whether the prices include Tax or not. Read-Only.|
|paymentTermsId|GUID|The id of the order payment term.|
|paymentTerms|string, maximum size 10|The payment terms of the order.|
|salesperson|string, maximum size 20|The salesperson code for the order.|
|partialShipping|boolean|Specifies whether partial shipping of items is preferred or not.|
|requestedDeliveryDate|Date|The requested delivery date.|
|discountAmount|numeric|The order discount amount|
|discountAppliedBeforeTax|boolean|Specifies whether the discount is applied before tax. Read-Only.|
|totalAmountExcludingTax|numeric|The total amount excluding tax. Read-Only.|
|totalTaxAmount|numeric|The total tax amount for the order. Read-Only.|
|totalAmountIncludingTax|numeric|The total amount for the order, including tax. Read-Only.|
|fullyShipped|boolean|Specifies whether the items of the order were fully shipped or not.|
|status|string, maximum size 20|The order status. Status can be: Draft, Cancelled, Paid, On hold, Created. Read-Only.|
|billToName             |string, maximum length 100   |The name of the customer to bill.|
|billToCustomerId       |GUID   |Id of the customer to bill|
|billToCustomerNumber   |string, maximum length 20   |Number of the customer to bill.|
|shipToName   |string, maximum size 100   |Name of the customer in ship to address.|
|shipToContact   |string, maximum size 100   |Ship to contact|
|sellingPostalAddress|Microsoft.NAV.postalAddressType| Selling postal address|
|billingPostalAddress|Microsoft.NAV.postalAddressType| Billing postal address|
|shippingPostalAddress|Microsoft.NAV.postalAddressType| Shipping postal adress|
|lastModifiedDateTime|datetime|The last datetime the sales order was modified. Read-Only.|


## JSON representation

Here is a JSON representation of the resource.


```json
{
   "id": "GUID",
   "number": "string",
   "externalDocumentNumber": "string",
   "orderDate": "date",
   "postingDate": "date",
   "customerId": "GUID",
   "customerNumber": "string",
   "customerName": "string",
   "billToName": "string",
   "billToCustomerId": "GUID",
   "billToCustomerNumber": "string",
   "shipToName": "string",
   "shipToContact": "string",
   "sellToAddressLine1": "string",
   "sellToAddressLine2": "string",
   "sellToCity": "string",
   "sellToCountry": "string",
   "sellToState": "string",
   "sellToPostCode": "string",
   "billToAddressLine1": "string",
   "billToAddressLine2": "string",
   "billToCity": "string",
   "billToCountry": "string",
   "billToState": "string",
   "billToPostCode": "string",
   "shipToAddressLine1": "string",
   "shipToAddressLine2": "string",
   "shipToCity": "string",
   "shipToCountry": "string",
   "shipToState": "string",
   "shipToPostCode": "string",
   "currencyId": "GUID",
   "currencyCode": "string",
   "pricesIncludeTax": "boolean",
   "paymentTermsId": "GUID",
   "shipmentMethodId": "GUID",
   "salesperson": "string",
   "partialShipping": "boolean",
   "requestedDeliveryDate": "date",
   "discountAmount": "decimal",
   "discountAppliedBeforeTax": "boolean",
   "totalAmountExcludingTax": "decimal",
   "totalTaxAmount": "decimal",
   "totalAmountIncludingTax": "decimal",
   "fullyShipped": "boolean",
   "status": "string",
   "lastModifiedDateTime": "datetime",
   "phoneNumber": "string",
   "email": "string"
}
```
## See also

[Get Sales Order](../api/dynamics_salesorder_get.md)  
[Create Sales Order](../api/dynamics_create_salesorder.md)  
[Update Sales Order](../api/dynamics_salesorder_update.md)  
[Delete Sales Order](../api/dynamics_salesorder_delete.md)  