---
title: purchaseInvoice resource type | Microsoft Docs
description: A purchase invoice object in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# purchaseInvoice resource type
Represents a purchase invoice in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)]. 

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method                                                             | Return Type    |Description                     |
|:-------------------------------------------------------------------|:---------------|:-------------------------------|
|[GET purchaseInvoice](../api/dynamics_purchaseinvoice_get.md)      |purchaseInvoice|Gets a purchase invoice object.|
|[POST purchaseInvoice](../api/dynamics_create_purchaseinvoice.md)  |purchaseInvoice|Creates a purchase invoice object.|
|[PATCH purchaseInvoice](../api/dynamics_purchaseinvoice_update.md) |purchaseInvoice|Updates a purchase invoice object.|
|[DELETE purchaseInvoice](../api/dynamics_purchaseinvoice_delete.md)|none            |Deletes a purchase invoice object.|

## Bound actions

|Action          |Return type   |Description         |
|----------------|--------------|--------------------|
|[GET pdfDocument](../api/dynamics_salesquote_pdfdocument.md)|pdfDocument|Gets a PDF document.|



## Navigation

| Navigation |Return Type| Description |
|:----------|:----------|:-----------------|
|[vendor](../resources/dynamics_vendor.md)|vendor   |Gets the vendor of the purchaseInvoice.|
|[countryRegion](../resources/dynamics_countryregion.md)|countryRegion   |Gets the countryregion of the purchaseInvoice.|
|[currency](../resources/dynamics_currency.md)|currency   |Gets the currency of the purchaseInvoice.|
|[purchaseInvoiceLines](../resources/dynamics_purchaseinvoicelines.md)|purchaseInvoiceLines   |Gets the purchaseinvoicelines of the purchaseInvoice.|
|[pdfDocument](../resources/dynamics_pdfdocument.md)|pdfDocument   |Gets the pdfdocument of the purchaseInvoice.|
|[attachments](../resources/dynamics_attachments.md)|attachments   |Gets the attachments of the purchaseInvoice.|
|[dimensionSetLines](../resources/dynamics_dimensionsetlines.md)|dimensionSetLines   |Gets the dimensionsetlines of the purchaseInvoice.|



## Properties

| Property              | Type              |Description                                                |
|:----------------------|:----------------------|:----------------------------------------------------------|
|id                     |GUID                   |The invoice ID. Read-Only.                                 |
|number                 |string, maximum size 20|The invoice number. Read-Only.                             |
|invoiceDate            |date                   |The invoice date                                           |
|dueDate                |date                   |The date the invoice is due.                               |
|vendorInvoiceNumber    |string, maximum size 35|The vendor sales order reference for the invoice           |
|vendorId               |GUID                   |The id of the invoice vendor.                              |
|vendorNumber           |string, maximum size 20|The vendor number for the invoice.                         |
|vendorName             |string, maximum size 50|The full name of the vendor. Read-Only.                    |
|buyFromAddress         |[NAV.PostalAddress](../resources/dynamics_complextypes.md)|The vendor's address.  |
|currencyId           |GUID|The currency Id for the invoice.                         |
|currencyCode           |string, maximum size 10|The currency code for the invoice.                         |
|status                 |string, maximum size 20|The invoice status. Status can be: Draft, In Review, Open, Paid, Canceled, or Corrective. Read-Only.|
|discountAmount         |numeric                |The invoice discount amount                                |
|discountAppliedBeforeTax|boolean               |Specifies whether the discount is applied before tax.      |
|totalAmountExcludingTax|numeric                |The total amount excluding tax. Read-Only.                 |
|totalTaxAmount         |numeric                |The total tax amount for the invoice. Read-Only.           |
|totalAmountIncludingTax|numeric                |The total amount for the invoice, including tax. Read-Only.|
|pricesIncludeTax       |boolean                |Specifies whether the prices include Tax or not. Read-Only.|
|paymentTerms           |string, maximum size 10|The payment terms of the invoice.                          |
|shipmentMethod         |string, maximum size 10|The shipment method of the invoice.                        |
|payToName|string, maximum size 100 |Pay to name of the invoice. |
|payToContact|string, maximum size 100 |Pay to contact|
|payToVendorId|GUID |Pay to vendor id. |
|payToVendorNumber|string, maximum size 20 |Pay to vendor number |
|shipToName|string, maximum size 100|Ship to name. |
|shipToContact|string, maximum size 100|Ship to contact. |
|buyFromAddress|NAV.postalAddressType |Buy from address. |
|payToAddress| |NAV.postalAddressType |Pay to address. |
|shipToAddress| |NAV.postalAddressType |Ship to address. |
|lastModifiedDateTime   |datetime               |The last datetime the purchase invoice was modified. Read-Only.|


## JSON representation

Here is a JSON representation of the resource.


```json
{
   "id": "GUID",
   "number": "string",
   "invoiceDate": "date",
   "postingDate": "date",
   "dueDate": "date",
   "vendorInvoiceNumber": "string",
   "vendorId": "GUID",
   "vendorNumber": "string",
   "vendorName": "string",
   "payToName": "string",
   "payToContact": "string",
   "payToVendorId": "GUID",
   "payToVendorNumber": "string",
   "shipToName": "string",
   "shipToContact": "string",
   "buyFromAddressLine1": "string",
   "buyFromAddressLine2": "string",
   "buyFromCity": "string",
   "buyFromCountry": "string",
   "buyFromState": "string",
   "buyFromPostCode": "string",
   "shipToAddressLine1": "string",
   "shipToAddressLine2": "string",
   "shipToCity": "string",
   "shipToCountry": "string",
   "shipToState": "string",
   "shipToPostCode": "string",
   "payToAddressLine1": "string",
   "payToAddressLine2": "string",
   "payToCity": "string",
   "payToCountry": "string",
   "payToState": "string",
   "payToPostCode": "string",
   "currencyId": "GUID",
   "currencyCode": "string",
   "pricesIncludeTax": "boolean",
   "discountAmount": "decimal",
   "discountAppliedBeforeTax": "boolean",
   "totalAmountExcludingTax": "decimal",
   "totalTaxAmount": "decimal",
   "totalAmountIncludingTax": "decimal",
   "status": "string",
   "lastModifiedDateTime": "datetime"
}
```
## See also

[Purchase Invoice](../resources/dynamics_purchaseinvoice.md)  
[Get Purchase Invoice](../api/dynamics_purchaseinvoice_get.md)  
[Create Purchase Invoice](../api/dynamics_create_purchaseinvoice.md)  
[Update Purchase Invoice](../api/dynamics_purchaseinvoice_update.md)  
[Delete Purchase Invoice](../api/dynamics_purchaseinvoice_delete.md)  