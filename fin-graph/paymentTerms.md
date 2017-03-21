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
|[Get paymentTerms](get-paymentTerms.md)|paymentTerms|Get a paymentTerms object.|
|[Create paymentTerms](create-paymentTerms.md)|paymentTerms|Create a paymentTerms object.|
|[Update paymentTerms](update-paymentTerms.md)|paymentTerms|Update a paymentTerms object.|
|[Delete paymentTerms](delete-paymentTerms.md)|none|Delete a paymentTerms object.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the paymentTerms. Read-Only.|
|code|string|Specify the payment term code. This code is printed where the payment terms are used.|
|displayName|string|Specify the payment term display name. This is printed where the payment terms are used.|
|dueDateCalculation|string|Specify the formula that is used to calculate the date that a payment must be made.|
|discountDateCalculation|string|Specify the formula that is used to calculate the date that a payment must be made in order to obtain a discount.|
|discountPercent|decimal|Specify the discount percentage that is applied for early payment of an invoice amount.|
|calculateDiscountOnCreditMemos|boolean|Specifies if the discount should be applied to credit memos. **True** indicates a discount will be given, **False** indicates a discount will not be given.|
|lastModifiedDateTime|datetime|The last datetime the paymentTerms was modified. Read-Only.|  


## Relationships
None

## JSON representation

Here is a JSON representation of the paymentTerms.


```json
{
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