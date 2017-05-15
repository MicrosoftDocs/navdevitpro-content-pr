---
title: Payment Terms resource type | Microsoft Docs
description: A Payment Terms object.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/08/2017
ms.author: solsen
---

# Payment Terms resource type
Represents a paymentTerms resource type in [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET paymentTerms](get-paymentterms.md)|paymentTerms|Get a Payment Terms.|
|[POST paymentTerms](create-paymentterms.md)|paymentTerms|Create a Payment Terms.|
|[PATCH paymentTerms](update-paymentterms.md)|paymentTerms|Update a Payment Terms.|
|[DELETE paymentTerms](delete-paymentterms.md)|none|Delete a Payment Terms.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the paymentTerms. Read-Only.|
|code|string|Specifies the payment term code. |
|displayName|string|Specifies the payment term display name.|
|dueDateCalculation|string|Specifies the formula that is used to calculate the date that a payment must be made.|
|discountDateCalculation|string|Specifies the formula that is used to calculate the date that a payment must be made in order to obtain a discount.|
|discountPercent|decimal|Specifies the discount percentage that is applied for early payment of an invoice amount.|
|calculateDiscountOnCreditMemos|boolean|Specifies if the discount should be applied to credit memos. **True** indicates a discount will be given, **False** indicates a discount will not be given.|
|lastModifiedDateTime|datetime|The last datetime the paymentTerms was modified. Read-Only.|  


## Relationships
None

## JSON representation

Here is a JSON representation of the paymentTerms.


```json
{
  "id": "GUID",
  "code": "string",
  "displayName": "string",
  "dueDateCalculation": "string",
  "discountDateCalculation": "string",
  "discountPercent": "decimal",
  "calculateDiscountOnCreditMemos": "boolean",
  "lastModifiedDateTime": "datetime"
}

```

## See Also
[Graph Reference](graph-reference.md)  
