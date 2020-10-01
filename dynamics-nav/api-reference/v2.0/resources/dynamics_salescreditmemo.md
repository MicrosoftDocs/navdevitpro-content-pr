---
title: salesCreditMemo resource type | Microsoft Docs
description: A sales credit memo object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: "dynamics365-business-central"
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/01/2020
ms.author: solsen
---

# salesCreditMemo resource type
Represents a sales credit memo in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods
| Method | Return Type|Description |
|:--------------------|:-----------|:-------------------------|
|[GET salesCreditMemo](../api/dynamics_salesCreditMemo_Get.md)|salesCreditMemo|Gets a sales credit memo object.|
|[DELETE salesCreditMemo](../api/dynamics_salesCreditMemo_Delete.md)|none|Deletes a sales credit memo object.|
|[POST salesCreditMemo](../api/dynamics_salesCreditMemo_Create.md)|salesCreditMemo|Creates a sales credit memo object.|
|[PATCH salesCreditMemo](../api/dynamics_salesCreditMemo_Update.md)|salesCreditMemo|Updates a sales credit memo object.|

## Navigation

| Navigation |Return Type| Description |    
|:----------|:----------|:-----------------|
|[customer](dynamics_customer.md)|customer |Gets the customer of the salesCreditMemo.|
|[countryRegion](dynamics_countryregion.md)|countryRegion |Gets the countryregion of the salesCreditMemo.|
|[currency](dynamics_currency.md)|currency |Gets the currency of the salesCreditMemo.|
|[paymentTerm](dynamics_paymentterm.md)|paymentTerm |Gets the paymentterm of the salesCreditMemo.|
|[shipmentMethod](dynamics_shipmentmethod.md)|shipmentMethod |Gets the shipmentmethod of the salesCreditMemo.|
|[salesCreditMemoLines](dynamics_salescreditmemolines.md)|salesCreditMemoLines |Gets the salescreditmemolines of the salesCreditMemo.|
|[pdfDocument](dynamics_pdfdocument.md)|pdfDocument |Gets the pdfdocument of the salesCreditMemo.|
|[dimensionSetLines](dynamics_dimensionsetlines.md)|dimensionSetLines |Gets the dimensionsetlines of the salesCreditMemo.|
|[attachments](dynamics_attachments.md)|attachments |Gets the attachments of the salesCreditMemo.|


## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|id|GUID|The unique ID of the item. Non-editable.|
|number|string|Specifies the number of the sales credit memo.|
|externalDocumentNumber|string|Specifies an external document number for the sales credit memo.|
|creditMemoDate|date|The credit memo date.|
|postingDate|date|The date that the sales credit memo   is posted.|
|dueDate|date|T he date the sales credit memo is due.|
|customerId|GUID|The unique ID of customer.  |
|customerNumber|string|The customer's number.|
|customerName|string|The customer's name.|
|billToName|string|Bill to name.|
|billToCustomerId|GUID|Bill to customer id.|
|billToCustomerNumber|string|Bill to customer number.|
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
|currencyId|GUID|Specifies which currency the sales credit memo uses.|
|currencyCode|string|The default currency code for the sales credit memo.|
|paymentTermsId|GUID|Specifies which payment term the sales credit memo uses.|
|shipmentMethodId|GUID|Specifies which shipment method the sales credit memo uses.|
|salesperson|string|The salesperson code for the sales credit memo.|
|pricesIncludeTax|boolean|Specifies whether the prices include Tax or not. Read-Only.|
|discountAmount|decimal|The sales credit memo discount amount.|
|discountAppliedBeforeTax|boolean|Specifies whether the discount is applied before tax.|
|totalAmountExcludingTax|decimal|The total amount excluding tax. Read-Only.  |
|totalTaxAmount|decimal|The total tax amount for the sales credit memo. Read-Only.|
|totalAmountIncludingTax|decimal|The total amount including tax. Read-Only.  |
|status|NAV.salesCrMemoEntityBufferStatus|Specifies the status of the sales credit memo. It can be "Draft" , "In Review", "Open", "Canceled", "Corrective", or "Paid".|
|lastModifiedDateTime|datetime|The last datetime the sales credit memo was modified. Read-Only.|
|invoiceId|GUID|The unique ID of invoice.|
|invoiceNumber|string|The sales invoice number that the sales credit memo  is linked to.|
|phoneNumber|string|Specifies the sales credit memo's telephone number.|
|email|string|Specifies the sales credit memo's email address.|


## JSON representation

Here is a JSON representation of the salesCreditMemo resource.


```json
{
   "id": "GUID",
   "number": "string",
   "externalDocumentNumber": "string",
   "creditMemoDate": "date",
   "postingDate": "date",
   "dueDate": "date",
   "customerId": "GUID",
   "customerNumber": "string",
   "customerName": "string",
   "billToName": "string",
   "billToCustomerId": "GUID",
   "billToCustomerNumber": "string",
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
   "currencyId": "GUID",
   "currencyCode": "string",
   "paymentTermsId": "GUID",
   "shipmentMethodId": "GUID",
   "salesperson": "string",
   "pricesIncludeTax": "boolean",
   "discountAmount": "decimal",
   "discountAppliedBeforeTax": "boolean",
   "totalAmountExcludingTax": "decimal",
   "totalTaxAmount": "decimal",
   "totalAmountIncludingTax": "decimal",
   "status": "NAV.salesCrMemoEntityBufferStatus",
   "lastModifiedDateTime": "datetime",
   "invoiceId": "GUID",
   "invoiceNumber": "string",
   "phoneNumber": "string",
   "email": "string"
}
```
## See also

[GET salesCreditMemo](../api/dynamics_salesCreditMemo_Get.md)   
[DELETE salesCreditMemo](../api/dynamics_salesCreditMemo_Delete.md)   
[POST salesCreditMemo](../api/dynamics_salesCreditMemo_Create.md)   
[PATCH salesCreditMemo](../api/dynamics_salesCreditMemo_Update.md)   

