---
title: entityMetadata resource type | Microsoft Docs
description: A purchase invoice line object in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# entityMetadata resource type
Represents a line on a purchase invoice in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET entityMetadata](../api/dynamics_purchaseinvoiceline_get.md)|entityMetadata|Gets a purchase invoice line object.|
|[POST entityMetadata](../api/dynamics_create_purchaseinvoiceline.md)|entityMetadata|Creates a purchase invoice line object.|
|[PATCH entityMetadata](../api/dynamics_purchaseinvoiceline_update.md)|entityMetadata|Updates a purchase invoice line object.|
|[DELETE entityMetadata](../api/dynamics_purchaseinvoiceline_delete.md)|none   |Deletes a purchase invoice line object.|


## Navigation

| Navigation |Return Type| Description |
|:----------|:----------|:-----------------|
|[items](../resources/dynamics_items.md)|items   |Gets the items of the entityMetadata.|
|[picture](../resources/dynamics_picture.md)|picture   |Gets the picture of the entityMetadata.|
|[defaultDimensions](../resources/dynamics_defaultdimensions.md)|defaultDimensions   |Gets the defaultdimensions of the entityMetadata.|
|[itemVariants](../resources/dynamics_itemvariants.md)|itemVariants   |Gets the itemvariants of the entityMetadata.|
|[customers](../resources/dynamics_customers.md)|customers   |Gets the customers of the entityMetadata.|
|[customerFinancialDetails](../resources/dynamics_customerfinancialdetails.md)|customerFinancialDetails   |Gets the customerfinancialdetails of the entityMetadata.|
|[agedAccountsReceivable](../resources/dynamics_agedaccountsreceivable.md)|agedAccountsReceivable   |Gets the agedaccountsreceivable of the entityMetadata.|
|[vendors](../resources/dynamics_vendors.md)|vendors   |Gets the vendors of the entityMetadata.|
|[agedAccountsPayable](../resources/dynamics_agedaccountspayable.md)|agedAccountsPayable   |Gets the agedaccountspayable of the entityMetadata.|
|[entityMetadataInformation](../resources/dynamics_entityMetadatainformation.md)|entityMetadataInformation   |Gets the entityMetadatainformation of the entityMetadata.|
|[salesInvoices](../resources/dynamics_salesinvoices.md)|salesInvoices   |Gets the salesinvoices of the entityMetadata.|
|[salesInvoiceLines](../resources/dynamics_salesinvoicelines.md)|salesInvoiceLines   |Gets the salesinvoicelines of the entityMetadata.|
|[dimensionSetLines](../resources/dynamics_dimensionsetlines.md)|dimensionSetLines   |Gets the dimensionsetlines of the entityMetadata.|
|[pdfDocument](../resources/dynamics_pdfdocument.md)|pdfDocument   |Gets the pdfdocument of the entityMetadata.|
|[attachments](../resources/dynamics_attachments.md)|attachments   |Gets the attachments of the entityMetadata.|
|[customerPaymentJournals](../resources/dynamics_customerpaymentjournals.md)|customerPaymentJournals   |Gets the customerpaymentjournals of the entityMetadata.|
|[customerPayments](../resources/dynamics_customerpayments.md)|customerPayments   |Gets the customerpayments of the entityMetadata.|
|[accounts](../resources/dynamics_accounts.md)|accounts   |Gets the accounts of the entityMetadata.|
|[taxGroups](../resources/dynamics_taxgroups.md)|taxGroups   |Gets the taxgroups of the entityMetadata.|
|[journals](../resources/dynamics_journals.md)|journals   |Gets the journals of the entityMetadata.|
|[journalLines](../resources/dynamics_journallines.md)|journalLines   |Gets the journallines of the entityMetadata.|
|[employees](../resources/dynamics_employees.md)|employees   |Gets the employees of the entityMetadata.|
|[timeRegistrationEntries](../resources/dynamics_timeregistrationentries.md)|timeRegistrationEntries   |Gets the timeregistrationentries of the entityMetadata.|
|[generalLedgerEntries](../resources/dynamics_generalledgerentries.md)|generalLedgerEntries   |Gets the generalledgerentries of the entityMetadata.|
|[currencies](../resources/dynamics_currencies.md)|currencies   |Gets the currencies of the entityMetadata.|
|[paymentMethods](../resources/dynamics_paymentmethods.md)|paymentMethods   |Gets the paymentmethods of the entityMetadata.|
|[dimensions](../resources/dynamics_dimensions.md)|dimensions   |Gets the dimensions of the entityMetadata.|
|[dimensionValues](../resources/dynamics_dimensionvalues.md)|dimensionValues   |Gets the dimensionvalues of the entityMetadata.|
|[paymentTerms](../resources/dynamics_paymentterms.md)|paymentTerms   |Gets the paymentterms of the entityMetadata.|
|[shipmentMethods](../resources/dynamics_shipmentmethods.md)|shipmentMethods   |Gets the shipmentmethods of the entityMetadata.|
|[itemCategories](../resources/dynamics_itemcategories.md)|itemCategories   |Gets the itemcategories of the entityMetadata.|
|[cashFlowStatement](../resources/dynamics_cashflowstatement.md)|cashFlowStatement   |Gets the cashflowstatement of the entityMetadata.|
|[countriesRegions](../resources/dynamics_countriesregions.md)|countriesRegions   |Gets the countriesregions of the entityMetadata.|
|[salesOrders](../resources/dynamics_salesorders.md)|salesOrders   |Gets the salesorders of the entityMetadata.|
|[salesOrderLines](../resources/dynamics_salesorderlines.md)|salesOrderLines   |Gets the salesorderlines of the entityMetadata.|
|[retainedEarningsStatement](../resources/dynamics_retainedearningsstatement.md)|retainedEarningsStatement   |Gets the retainedearningsstatement of the entityMetadata.|
|[unitsOfMeasure](../resources/dynamics_unitsofmeasure.md)|unitsOfMeasure   |Gets the unitsofmeasure of the entityMetadata.|
|[balanceSheet](../resources/dynamics_balancesheet.md)|balanceSheet   |Gets the balancesheet of the entityMetadata.|
|[trialBalance](../resources/dynamics_trialbalance.md)|trialBalance   |Gets the trialbalance of the entityMetadata.|
|[incomeStatement](../resources/dynamics_incomestatement.md)|incomeStatement   |Gets the incomestatement of the entityMetadata.|
|[taxAreas](../resources/dynamics_taxareas.md)|taxAreas   |Gets the taxareas of the entityMetadata.|
|[salesQuotes](../resources/dynamics_salesquotes.md)|salesQuotes   |Gets the salesquotes of the entityMetadata.|
|[salesQuoteLines](../resources/dynamics_salesquotelines.md)|salesQuoteLines   |Gets the salesquotelines of the entityMetadata.|
|[salesCreditMemos](../resources/dynamics_salescreditmemos.md)|salesCreditMemos   |Gets the salescreditmemos of the entityMetadata.|
|[salesCreditMemoLines](../resources/dynamics_salescreditmemolines.md)|salesCreditMemoLines   |Gets the salescreditmemolines of the entityMetadata.|
|[purchaseInvoices](../resources/dynamics_purchaseinvoices.md)|purchaseInvoices   |Gets the purchaseinvoices of the entityMetadata.|
|[purchaseInvoiceLines](../resources/dynamics_purchaseinvoicelines.md)|purchaseInvoiceLines   |Gets the purchaseinvoicelines of the entityMetadata.|
|[projects](../resources/dynamics_projects.md)|projects   |Gets the projects of the entityMetadata.|
|[bankAccounts](../resources/dynamics_bankaccounts.md)|bankAccounts   |Gets the bankaccounts of the entityMetadata.|
|[customerSales](../resources/dynamics_customersales.md)|customerSales   |Gets the customersales of the entityMetadata.|
|[vendorPurchases](../resources/dynamics_vendorpurchases.md)|vendorPurchases   |Gets the vendorpurchases of the entityMetadata.|

## Properties

| Property     | Type   |Description|
|:---------------|:--------|:----------|
|documentId|GUID|The ID of the parent invoice.|
|sequence|numeric|The line sequence number.|
|itemId|GUID|The Id of the item in the invoice line.|
|accountId|GUID|The Id of the Account that will be used for this line. lineType will automatically be set to "Account" if this is set.|
|lineType|string|The type of the line. Can be Comment,Account,Item,Resource,Fixed Asset,Charge|
|lineDetails|complex|The details of the line.|
|description|string|A description of the item in the invoice line.|
|unitOfMeasure|[NAV.UnitOfMeasure](../resources/dynamics_complextypes.md)|The unit of measure complex type.|
|unitCost|numeric|The unit cost of each individual item in the invoice line.|
|quantity|numeric|The quantity of the item in the invoice line.|
|discountAmount|numeric|The line discount amount.|
|discountPercent|numeric|The line discount percent.|
|discountAppliedBeforeTax|boolean|Specified if the discount is applied before tax. Read-Only.|
|amountExcludingTax|numeric|The line amount excluding the tax. Read-Only.|
|taxCode|string|The tax code for the line.|
|taxPercent|numeric|The tax percent for the line. Read-Only.|
|totalTaxAmount|numeric|The total tax amount for the line. Read-Only.|
|amountIncludingTax|numeric|The total amount for the line including tax. Read-Only.|
|invoiceDiscountAllocation|numeric|The invoice discount allocation is the invoice discount distributed on the total amount. Read-Only.|
|netAmount|numeric|The net amount is the amount including all discounts (taken from invoice header). Read-Only.|
|netTaxAmount|numeric|The net tax amount is the tax amount calculated from net amount. Read-Only.|
|netAmountIncludingTax|numeric|The net amount including tax is the total net amount including tax. Read-Only.|
|expectedReceiptDate|date|The date the item in the line is expected to be received.|

## JSON representation

Here is a JSON representation of the resource.


```json
  "value": [
    {
   "entityName": "string",
   "entitySetName": "string",
   "entityCaptions": "NAV.entityMetadataLabel",
   "entitySetCaptions": "NAV.entityMetadataLabel",
   "properties": "NAV.entityMetadataField",
   "actions": "NAV.entityMetadataAction",
   "enumMembers": "NAV.entityMetadataEnumMember"
}
  ]
```

## See also

[Get Purchase Invoice Line](../api/dynamics_purchaseinvoiceline_get.md)  
[Create Purchase Invoice Line](../api/dynamics_create_purchaseinvoiceline.md)  
[Update Purchase Invoice Line](../api/dynamics_purchaseinvoiceline_update.md)  
[Delete Purchase Invoice Line](../api/dynamics_purchaseinvoiceline_delete.md)  