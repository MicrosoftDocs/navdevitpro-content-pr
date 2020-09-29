---
title: dimensionSetLine resource type | Microsoft Docs
description: A dimension set line object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: "dynamics365-business-central"
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/01/2020
ms.author: solsen
---

# dimensionSetLine resource type
Represents a dimension set line in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods
| Method | Return Type|Description |
|:--------------------|:-----------|:-------------------------|
|[GET dimensionSetLine](../api/dynamics_dimensionSetLine_Get.md)|dimensionSetLine|Gets a dimension set line object.|
|[DELETE dimensionSetLine](../api/dynamics_dimensionSetLine_Delete.md)|none|Deletes a dimension set line object.|
|[POST dimensionSetLine](../api/dynamics_dimensionSetLine_Create.md)|dimensionSetLine|Creates a dimension set line object.|
|[PATCH dimensionSetLine](../api/dynamics_dimensionSetLine_Update.md)|dimensionSetLine|Updates a dimension set line object.|




## Navigation

| Navigation |Return Type| Description |    
|:----------|:----------|:-----------------|
|[salesInvoice](../resources/dynamics_salesinvoice.md)|salesInvoice |Gets the salesinvoice of the dimensionSetLine.|
|[salesInvoiceLine](../resources/dynamics_salesinvoiceline.md)|salesInvoiceLine |Gets the salesinvoiceline of the dimensionSetLine.|
|[dimension](../resources/dynamics_dimension.md)|dimension |Gets the dimension of the dimensionSetLine.|
|[customerPayment](../resources/dynamics_customerpayment.md)|customerPayment |Gets the customerpayment of the dimensionSetLine.|
|[journalLine](../resources/dynamics_journalline.md)|journalLine |Gets the journalline of the dimensionSetLine.|
|[timeRegistrationEntry](../resources/dynamics_timeregistrationentry.md)|timeRegistrationEntry |Gets the timeregistrationentry of the dimensionSetLine.|
|[generalLedgerEntry](../resources/dynamics_generalledgerentry.md)|generalLedgerEntry |Gets the generalledgerentry of the dimensionSetLine.|
|[salesOrder](../resources/dynamics_salesorder.md)|salesOrder |Gets the salesorder of the dimensionSetLine.|
|[salesOrderLine](../resources/dynamics_salesorderline.md)|salesOrderLine |Gets the salesorderline of the dimensionSetLine.|
|[salesQuote](../resources/dynamics_salesquote.md)|salesQuote |Gets the salesquote of the dimensionSetLine.|
|[salesQuoteLine](../resources/dynamics_salesquoteline.md)|salesQuoteLine |Gets the salesquoteline of the dimensionSetLine.|
|[salesCreditMemo](../resources/dynamics_salescreditmemo.md)|salesCreditMemo |Gets the salescreditmemo of the dimensionSetLine.|
|[salesCreditMemoLine](../resources/dynamics_salescreditmemoline.md)|salesCreditMemoLine |Gets the salescreditmemoline of the dimensionSetLine.|
|[purchaseInvoice](../resources/dynamics_purchaseinvoice.md)|purchaseInvoice |Gets the purchaseinvoice of the dimensionSetLine.|
|[purchaseInvoiceLine](../resources/dynamics_purchaseinvoiceline.md)|purchaseInvoiceLine |Gets the purchaseinvoiceline of the dimensionSetLine.|


## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|id|GUID|The unique ID of the item. Non-editable.|
|code|string|The code of the dimension set line.|
|parentId|GUID|The ID of the parent entity. |
|parentType|NAV.dimensionSetEntryBufferParentType|The type of the parent document of the dimension set line. It can be " ", "Journal Line", "Sales Order", "Sales Order Line", "Sales Quote", "Sales Quote Line", "Sales Credit Memo", "Sales Credit Memo Line", "Sales Invoice", "Sales Invoice Line", "Purchase Invoice", "Purchase Invoice Line", "General Ledger Entry" or "Time Registration Entry".|
|displayName|string|Specifies the dimension set line's name. This name will appear on all sales documents for the dimension set line.|
|valueId|GUID|The unique ID of the value of the dimension.  |
|valueCode|string|The code of the value of the dimension.  |
|valueDisplayName|string|The display name of the value of the dimension. Read-Only.|


## JSON representation

Here is a JSON representation of the dimensionSetLine resource.


```json
{
   "id": "GUID",
   "code": "string",
   "parentId": "GUID",
   "parentType": "NAV.dimensionSetEntryBufferParentType",
   "displayName": "string",
   "valueId": "GUID",
   "valueCode": "string",
   "valueDisplayName": "string"
}
```
## See also

[GET dimensionSetLine](../api/dynamics_dimensionSetLine_Get.md)   
[DELETE dimensionSetLine](../api/dynamics_dimensionSetLine_Delete.md)   
[POST dimensionSetLine](../api/dynamics_dimensionSetLine_Create.md)   
[PATCH dimensionSetLine](../api/dynamics_dimensionSetLine_Update.md)   

