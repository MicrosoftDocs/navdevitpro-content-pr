---
title: salesOrder resource type | Microsoft Docs
description: A sales order object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/01/2020
ms.author: solsen
---

# salesOrder resource type
Represents a sales order in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods
| Method | Return Type|Description |
|:--------------------|:-----------|:-------------------------|
|[GET salesOrder](../api/dynamics_salesOrder_Get.md)|salesOrder|Gets a sales order object.|
|[DELETE salesOrder](../api/dynamics_salesOrder_Delete.md)|none|Deletes a sales order object.|
|[POST salesOrder](../api/dynamics_salesOrder_Create.md)|salesOrder|Creates a sales order object.|
|[PATCH salesOrder](../api/dynamics_salesOrder_Update.md)|salesOrder|Updates a sales order object.|




## Navigation

| Navigation |Return Type| Description |    
|:----------|:----------|:-----------------|
|[customer](../resources/dynamics_customer.md)|customer |Gets the customer of the salesOrder.|
|[countryRegion](../resources/dynamics_countryregion.md)|countryRegion |Gets the countryregion of the salesOrder.|
|[currency](../resources/dynamics_currency.md)|currency |Gets the currency of the salesOrder.|
|[paymentTerm](../resources/dynamics_paymentterm.md)|paymentTerm |Gets the paymentterm of the salesOrder.|
|[shipmentMethod](../resources/dynamics_shipmentmethod.md)|shipmentMethod |Gets the shipmentmethod of the salesOrder.|
|[salesOrderLines](../resources/dynamics_salesorderlines.md)|salesOrderLines |Gets the salesorderlines of the salesOrder.|
|[attachments](../resources/dynamics_attachments.md)|attachments |Gets the attachments of the salesOrder.|
|[dimensionSetLines](../resources/dynamics_dimensionsetlines.md)|dimensionSetLines |Gets the dimensionsetlines of the salesOrder.|


## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|id|GUID|The unique ID of the item. Non-editable.|
|number|string|Specifies the number of the sales order.|
|externalDocumentNumber|string|Specifies an external document number for the sales order.|
|orderDate|date|The order date.|
|postingDate|date|The date that the sales order   is posted.|
|customerId|GUID|The unique ID of customer.  |
|customerNumber|string|The customer's number.|
|customerName|string|The customer's name.|
|billToName|string|Bill to name.|
|billToCustomerId|GUID|Bill to customer id.|
|billToCustomerNumber|string|Bill to customer number.|
|shipToName|string|Ship to name.|
|shipToContact|string|Ship to contact.|
|sellToAddressLine1|string|Sell to address line 1.|
|sellToAddressLine2|string|Sell to address line 2.|
|sellToCity|string|Sell to city.|
|sellToCountry|string|Sell to country.|
|sellToState|string|Sell to state.|
|sellToPostCode|string|Sell to post code.|
|billToAddressLine1|string|Bill to address line 1.|
|billToAddressLine2|string|Bill to address line 2.|
|billToCity|string|Bill to city.|
|billToCountry|string|Bill to country.|
|billToState|string|Bill to state.|
|billToPostCode|string|Bill to post code.|
|shipToAddressLine1|string|Ship to address line 1.|
|shipToAddressLine2|string|Ship to address line 2.|
|shipToCity|string|Ship to city.|
|shipToCountry|string|Ship to country.|
|shipToState|string|Ship to state.|
|shipToPostCode|string|Ship to post code.|
|currencyId|GUID|Specifies which currency the sales order uses.|
|currencyCode|string|The default currency code for the sales order.|
|pricesIncludeTax|boolean|Specifies whether the prices include Tax or not. Read-Only.|
|paymentTermsId|GUID|Specifies which payment term the sales order uses.|
|shipmentMethodId|GUID|Specifies which shipment method the sales order uses.|
|salesperson|string|The salesperson code for the sales order.|
|partialShipping|boolean|Specifies whether partial shipping of items is preferred or not.|
|requestedDeliveryDate|date|The requested delivery date.|
|discountAmount|decimal|The sales order discount amount.|
|discountAppliedBeforeTax|boolean|Specifies whether the discount is applied before tax.|
|totalAmountExcludingTax|decimal|The total amount excluding tax. Read-Only.  |
|totalTaxAmount|decimal|The total tax amount for the sales order. Read-Only.|
|totalAmountIncludingTax|decimal|The total amount including tax. Read-Only.  |
|fullyShipped|boolean|Specifies whether the items of the sales order were fully shipped or not.|
|status|NAV.salesOrderEntityBufferStatus|Specifies the status of the sales order. It can be "Draft", "In Review" or "Open".|
|lastModifiedDateTime|datetime|The last datetime the sales order was modified. Read-Only.|
|phoneNumber|string|Specifies the sales order's telephone number.|
|email|string|Specifies the sales order's email address.|


## JSON representation

Here is a JSON representation of the salesOrder resource.


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
   "status": "NAV.salesOrderEntityBufferStatus",
   "lastModifiedDateTime": "datetime",
   "phoneNumber": "string",
   "email": "string"
}
```
## See also

[GET salesOrder](../api/dynamics_salesOrder_Get.md)
[DELETE salesOrder](../api/dynamics_salesOrder_Delete.md)
[POST salesOrder](../api/dynamics_salesOrder_Create.md)
[PATCH salesOrder](../api/dynamics_salesOrder_Update.md)

