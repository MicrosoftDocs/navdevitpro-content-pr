---
title: salesCreditMemo resource type | Microsoft Docs
description: A sales credit memo object in Dynamics 365 Business Central. 
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# salesCreditMemo resource type
Represents a sales credit memo in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)]. 

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET salesCreditMemo](../api/dynamics_salescreditmemo_get.md)|salesCreditMemo|Gets a sales credit memo object.|
|[POST salesCreditMemo](../api/dynamics_create_salescreditmemo.md)|salesCreditMemo|Creates a sales credit memo object.|
|[PATCH salesCreditMemo](../api/dynamics_salescreditmemo_update.md)|salesCreditMemo|Update a sales credit memo object.|
|[DELETE salesCreditMemo](../api/dynamics_salescreditmemo_delete.md)|none|Delete a sales credit memo object.|

## Bound actions

|Action          |Return type   |Description         |
|----------------|--------------|--------------------|
|[GET pdfDocument](../api/dynamics_salesquote_pdfdocument.md)|pdfDocument|Gets a PDF document.|



## Navigation

| Navigation |Return Type| Description |
|:----------|:----------|:-----------------|
|[customer](../resources/dynamics_customer.md)|customer   |Gets the customer of the salesCreditMemo.|
|[countryRegion](../resources/dynamics_countryregion.md)|countryRegion   |Gets the countryregion of the salesCreditMemo.|
|[currency](../resources/dynamics_currency.md)|currency   |Gets the currency of the salesCreditMemo.|
|[paymentTerm](../resources/dynamics_paymentterm.md)|paymentTerm   |Gets the paymentterm of the salesCreditMemo.|
|[shipmentMethod](../resources/dynamics_shipmentmethod.md)|shipmentMethod   |Gets the shipmentmethod of the salesCreditMemo.|
|[salesCreditMemoLines](../resources/dynamics_salescreditmemolines.md)|salesCreditMemoLines   |Gets the salescreditmemolines of the salesCreditMemo.|
|[pdfDocument](../resources/dynamics_pdfdocument.md)|pdfDocument   |Gets the pdfdocument of the salesCreditMemo.|
|[attachments](../resources/dynamics_attachments.md)|attachments   |Gets the attachments of the salesCreditMemo.|
|[dimensionSetLines](../resources/dynamics_dimensionsetlines.md)|dimensionSetLines   |Gets the dimensionsetlines of the salesCreditMemo.|



## Properties

| Property     | Type   |Description|
|:---------------|:--------|:----------|
|id|GUID|The credit memo ID. Non-editable.|
|number|string, maximum size 20|The credit memo number. Read-Only.|
|creditMemoDate|date|The credit memo date|
|dueDate|date|The date the credit memo is due.|
|customerId|GUID|The id of the credit memo customer.|
|contactId|string, maximum size 250|The exchange contact id for the given customer. If a customer id is not specified, we will use the contact id to find it.|
|customerNumber|string, maximum size 20|The customer number for the credit memo.|
|customerName|string, maximum size 50|The full name of the customer. Read-Only.|
|currencyId|GUID|The id of the credit memo currency.|
|currencyCode|string, maximum size 10|The currency code for the credit memo.|
|paymentTermsId|GUID|The id of the credit memo payment term.|
|paymentTerms|string, maximum size 10|The payment terms of the credit memo.|
|salesperson|string, maximum size 20|The salesperson code for the credit memo.|
|pricesIncludeTax|boolean|Specifies whether the prices include Tax or not. Read-Only.|
|discountAmount|numeric|The credit memo discount amount|
|discountAppliedBeforeTax|boolean|Specifies whether the discount is applied before tax.|
|totalAmountExcludingTax|numeric|The total amount excluding tax. Read-Only.|
|totalTaxAmount|numeric|The total tax amount for the credit memo. Read-Only.|
|totalAmountIncludingTax|numeric|The total amount for the credit memo, including tax. Read-Only.|
|status|string, maximum size 20|The credit memo status. Status can be: Draft, In Review, Open, Paid, Canceled, or Corrective. Read-Only.|
|invoiceId|GUID|The sales invoice ID that the credit memo is linked to.|
|invoiceNumber|GUID|The sales invoice number that the credit memo is linked to.|
|email           |string, maximum size 80|Email for the customer, cash sales|             |
|phone           |string, maximum size 30|Phone number for the customer, cash sales| 
|billToName             |string, maximum length 100   |The name of the customer to bill.|
|billToCustomerId       |GUID   |Id of the customer to bill|
|billToCustomerNumber   |string, maximum length 20   |Number of the customer to bill.|
|sellingPostalAddress|Microsoft.NAV.postalAddressType| Selling postal address|
|billingPostalAddress|complex|The billing postal address for the credit memo.|
|lastModifiedDateTime|datetime|The last datetime the sales credit memo was modified. Read-Only.|


## JSON representation

Here is a JSON representation of the resource.


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
   "status": "string",
   "lastModifiedDateTime": "datetime",
   "invoiceId": "GUID",
   "invoiceNumber": "string",
   "phoneNumber": "string",
   "email": "string"
}
```
## See also

[Get Sales Credit Memo](../api/dynamics_salescreditmemo_get.md)  
[Create Sales Credit Memo](../api/dynamics_create_salescreditmemo.md)  
[Update Sales Credit Memo](../api/dynamics_salescreditmemo_update.md)  
[Delete Sales Credit Memo](../api/dynamics_salescreditmemo_delete.md)  