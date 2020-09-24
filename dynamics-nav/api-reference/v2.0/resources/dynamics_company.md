---
title: company resource type | Microsoft Docs
description: A company object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/24/2020
ms.author: solsen
---

# company resource type
Represents a company in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods
| Method | Return Type|Description |
|:--------------------|:-----------|:-------------------------|
|[GET company](../api/dynamics_company_Get.md)|company|Gets a company object.|




## Navigation

| Navigation |Return Type| Description |    
|:----------|:----------|:-----------------|
|[items](../resources/dynamics_items.md)|items |Gets the items of the company.|
|[unitsOfMeasure](../resources/dynamics_unitsofmeasure.md)|unitsOfMeasure |Gets the unitsofmeasure of the company.|
|[pictures](../resources/dynamics_pictures.md)|pictures |Gets the pictures of the company.|
|[defaultDimensions](../resources/dynamics_defaultdimensions.md)|defaultDimensions |Gets the defaultdimensions of the company.|
|[itemVariants](../resources/dynamics_itemvariants.md)|itemVariants |Gets the itemvariants of the company.|
|[customers](../resources/dynamics_customers.md)|customers |Gets the customers of the company.|
|[customerFinancialDetails](../resources/dynamics_customerfinancialdetails.md)|customerFinancialDetails |Gets the customerfinancialdetails of the company.|
|[agedAccountsReceivables](../resources/dynamics_agedaccountsreceivables.md)|agedAccountsReceivables |Gets the agedaccountsreceivables of the company.|
|[vendors](../resources/dynamics_vendors.md)|vendors |Gets the vendors of the company.|
|[agedAccountsPayables](../resources/dynamics_agedaccountspayables.md)|agedAccountsPayables |Gets the agedaccountspayables of the company.|
|[companyInformation](../resources/dynamics_companyinformation.md)|companyInformation |Gets the companyinformation of the company.|
|[salesInvoices](../resources/dynamics_salesinvoices.md)|salesInvoices |Gets the salesinvoices of the company.|
|[salesInvoiceLines](../resources/dynamics_salesinvoicelines.md)|salesInvoiceLines |Gets the salesinvoicelines of the company.|
|[dimensionSetLines](../resources/dynamics_dimensionsetlines.md)|dimensionSetLines |Gets the dimensionsetlines of the company.|
|[pdfDocument](../resources/dynamics_pdfdocument.md)|pdfDocument |Gets the pdfdocument of the company.|
|[attachments](../resources/dynamics_attachments.md)|attachments |Gets the attachments of the company.|
|[customerPaymentJournals](../resources/dynamics_customerpaymentjournals.md)|customerPaymentJournals |Gets the customerpaymentjournals of the company.|
|[customerPayments](../resources/dynamics_customerpayments.md)|customerPayments |Gets the customerpayments of the company.|
|[accounts](../resources/dynamics_accounts.md)|accounts |Gets the accounts of the company.|
|[taxGroups](../resources/dynamics_taxgroups.md)|taxGroups |Gets the taxgroups of the company.|
|[journals](../resources/dynamics_journals.md)|journals |Gets the journals of the company.|
|[journalLines](../resources/dynamics_journallines.md)|journalLines |Gets the journallines of the company.|
|[employees](../resources/dynamics_employees.md)|employees |Gets the employees of the company.|
|[timeRegistrationEntries](../resources/dynamics_timeregistrationentries.md)|timeRegistrationEntries |Gets the timeregistrationentries of the company.|
|[generalLedgerEntries](../resources/dynamics_generalledgerentries.md)|generalLedgerEntries |Gets the generalledgerentries of the company.|
|[currencies](../resources/dynamics_currencies.md)|currencies |Gets the currencies of the company.|
|[paymentMethods](../resources/dynamics_paymentmethods.md)|paymentMethods |Gets the paymentmethods of the company.|
|[dimensions](../resources/dynamics_dimensions.md)|dimensions |Gets the dimensions of the company.|
|[dimensionValues](../resources/dynamics_dimensionvalues.md)|dimensionValues |Gets the dimensionvalues of the company.|
|[paymentTerms](../resources/dynamics_paymentterms.md)|paymentTerms |Gets the paymentterms of the company.|
|[shipmentMethods](../resources/dynamics_shipmentmethods.md)|shipmentMethods |Gets the shipmentmethods of the company.|
|[itemCategories](../resources/dynamics_itemcategories.md)|itemCategories |Gets the itemcategories of the company.|
|[cashFlowStatements](../resources/dynamics_cashflowstatements.md)|cashFlowStatements |Gets the cashflowstatements of the company.|
|[countriesRegions](../resources/dynamics_countriesregions.md)|countriesRegions |Gets the countriesregions of the company.|
|[salesOrders](../resources/dynamics_salesorders.md)|salesOrders |Gets the salesorders of the company.|
|[salesOrderLines](../resources/dynamics_salesorderlines.md)|salesOrderLines |Gets the salesorderlines of the company.|
|[retainedEarningsStatements](../resources/dynamics_retainedearningsstatements.md)|retainedEarningsStatements |Gets the retainedearningsstatements of the company.|
|[balanceSheets](../resources/dynamics_balancesheets.md)|balanceSheets |Gets the balancesheets of the company.|
|[trialBalances](../resources/dynamics_trialbalances.md)|trialBalances |Gets the trialbalances of the company.|
|[incomeStatements](../resources/dynamics_incomestatements.md)|incomeStatements |Gets the incomestatements of the company.|
|[taxAreas](../resources/dynamics_taxareas.md)|taxAreas |Gets the taxareas of the company.|
|[salesQuotes](../resources/dynamics_salesquotes.md)|salesQuotes |Gets the salesquotes of the company.|
|[salesQuoteLines](../resources/dynamics_salesquotelines.md)|salesQuoteLines |Gets the salesquotelines of the company.|
|[salesCreditMemos](../resources/dynamics_salescreditmemos.md)|salesCreditMemos |Gets the salescreditmemos of the company.|
|[salesCreditMemoLines](../resources/dynamics_salescreditmemolines.md)|salesCreditMemoLines |Gets the salescreditmemolines of the company.|
|[purchaseInvoices](../resources/dynamics_purchaseinvoices.md)|purchaseInvoices |Gets the purchaseinvoices of the company.|
|[purchaseInvoiceLines](../resources/dynamics_purchaseinvoicelines.md)|purchaseInvoiceLines |Gets the purchaseinvoicelines of the company.|
|[projects](../resources/dynamics_projects.md)|projects |Gets the projects of the company.|
|[bankAccounts](../resources/dynamics_bankaccounts.md)|bankAccounts |Gets the bankaccounts of the company.|
|[customerSales](../resources/dynamics_customersales.md)|customerSales |Gets the customersales of the company.|
|[vendorPurchases](../resources/dynamics_vendorpurchases.md)|vendorPurchases |Gets the vendorpurchases of the company.|


## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|id|GUID|The unique ID of the item. Non-editable.|
|systemVersion|string|Specifies the internal version of the company.|
|name|string|Represents the company's name.|
|displayName|string|Specifies the company's name. This name will appear on all sales documents for the company.|
|businessProfileId|string|Specifies the Business Profile ID linked to the company.|
|systemCreatedAt|datetime|The datetime the company was created.|
|systemCreatedBy|GUID|The ID of the user who created the company.|
|systemModifiedAt|datetime|The last datetime the company was modified.|
|systemModifiedBy|GUID|The ID of the user who last modified the company.|


## JSON representation

Here is a JSON representation of the company resource.


```json
{
   "id": "GUID",
   "systemVersion": "string",
   "name": "string",
   "displayName": "string",
   "businessProfileId": "string",
   "systemCreatedAt": "datetime",
   "systemCreatedBy": "GUID",
   "systemModifiedAt": "datetime",
   "systemModifiedBy": "GUID"
}
```
## See also

[GET company](../api/dynamics_company_Get.md)

