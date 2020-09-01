---
title: customerPaymentJournal resource type | Microsoft Docs
description: A sales invoice line in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# customerPaymentJournal resource type
Represents a line on a sales invoice in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method                                                                | Return Type      | Description                    |
|:----------------------------------------------------------------------|:-----------------|:-------------------------------|
|[GET customerPaymentJournal](../api/dynamics_salesinvoiceline_get.md)      |customerPaymentJournal|Gets a sales invoice line object   |
|[POST customerPaymentJournal](../api/dynamics_create_salesinvoiceline.md)  |customerPaymentJournal|Creates a sales invoice line object.|
|[PATCH customerPaymentJournal](../api/dynamics_salesinvoiceline_update.md) |customerPaymentJournal|Updated a sales invoice line object.|
|[DELETE customerPaymentJournal](../api/dynamics_salesinvoiceline_delete.md)|none              |Deletes a sales invoice line object.|


## Navigation

| Navigation |Return Type| Description |
|:----------|:----------|:-----------------|
|[account](../resources/dynamics_account.md)|account   |Gets the account of the customerPaymentJournal.|
|[customerPayments](../resources/dynamics_customerpayments.md)|customerPayments   |Gets the customerpayments of the customerPaymentJournal.|

## Properties

| Property                | Type    | Description                                               |
|:------------------------|:------|:----------------------------------------------------------|
|documentId               |GUID   |The ID of the parent invoice.                              |
|sequence                 |numeric|The line sequence number.                                  |
|itemId                   |GUID   |The Id of the item in the invoice line.                    |
|accountId                |GUID   |The Id of the Account that will be used for this line. lineType will automatically be set to "Account" if this is set.|
|lineType                 |string |The type of the line. Can be Comment,Account,Item,Resource,Fixed Asset,Charge|
|lineDetails              |complex|The details of the line.                                   |
|description              |string |A description of the item in the invoice line.             |
|unitOfMeasureId          |GUID   |The unit of measure for the invoice line.                  |
|unitOfMeasure            |[NAV.UnitOfMeasure](../resources/dynamics_complextypes.md)|The unit of measure complex type.|
|quantity                 |numeric|The quantity of the item in the invoice line.              |
|unitPrice                |numeric|The unit price of each individual item in the invoice line.|
|discountAmount           |numeric|The line discount amount.                                  |
|discountPercent          |numeric|The line discount percent.                                 |
|discountAppliedBeforeTax |boolean|Specified if the discount is applied before tax. Read-Only.|
|amountExcludingTax       |numeric|The line amount excluding the tax. Read-Only.              |
|taxCode                  |string |The tax code for the line.                                 |
|taxPercent               |numeric|The tax percent for the line. Read-Only.                   |
|totalTaxAmount           |numeric|The total tax amount for the line. Read-Only.              |
|amountIncludingTax       |numeric|The total amount for the line including tax. Read-Only.    |
|invoiceDiscountAllocation|numeric|The invoice discount allocation is the invoice discount distributed on the total amount. Read-Only.|
|netAmount                |numeric|The net amount is the amount including all discounts (taken from invoice header). Read-Only.|
|netTaxAmount             |numeric|The net tax amount is the tax amount calculated from net amount. Read-Only.|
|netAmountIncludingTax    |numeric|The net amount including tax is the total net amount including tax. Read-Only.|
|shipmentDate             |date   |The date the item in the line is expected to ship.         |

## JSON representation

Here is a JSON representation of the resource.


```json
  "value": [
    {
   "id": "GUID",
   "code": "string",
   "displayName": "string",
   "lastModifiedDateTime": "datetime",
   "balancingAccountId": "GUID",
   "balancingAccountNumber": "string"
}
  ]
```

## See also

[Get Sales Invoice Line](../api/dynamics_salesinvoiceline_get.md)  
[Create Sales Invoice Line](../api/dynamics_create_salesinvoiceline.md)  
[Update Sales Invoice Line](../api/dynamics_salesinvoiceline_update.md)  
[Delete Sales Invoice Line](../api/dynamics_salesinvoiceline_delete.md)  