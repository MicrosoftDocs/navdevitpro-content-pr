---
title: paymentTerms resource type | Microsoft Docs
description: A payment terms object in Dynamics 365 for Financials.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/11/2017
ms.author: solsen
---

# paymentTerms resource type
Represents a payment term in Dynamics 365 for Financials.

## Methods

| Method                                                      | Return Type|Description            |
|:------------------------------------------------------------|:-----------|:----------------------|
|[GET paymentTerms](../api/dynamics_paymentterms_get.md)      |paymentTerms|Get a payment terms object.   |
|[POST paymentTerms](../api/dynamics_create_paymentterms.md)  |paymentTerms|Create a payment terms object.|
|[PATCH paymentTerms](../api/dynamics_paymentterms_update.md) |paymentTerms|Update a payment terms object.|
|[DELETE paymentTerms](../api/dynamics_paymentterms_delete.md)|none        |Delete a payment terms object.|

## Properties
| Property	                   | Type	  |Description                                                |
|:-----------------------------|:-------|:----------------------------------------------------------|
|id                            |GUID    |The unique ID of the paymentTerms. Non-editable.           |
|code                          |string  |Specifies the payment term code.                           |
|displayName                   |string  |Specifies the payment term display name.                   |
|dueDateCalculation            |string  |Specifies the formula that is used to calculate the date that a payment must be made.|
|discountDateCalculation       |string  |Specifies the formula that is used to calculate the date that a payment must be made in order to obtain a discount.|
|discountPercent               |decimal |Specifies the discount percentage that is applied for early payment of an invoice amount.|
|calculateDiscountOnCreditMemos|boolean |Specifies if the discount should be applied to credit memos. **True** indicates a discount will be given, **false** indicates a discount will not be given.|
|lastModifiedDateTime          |datetime|The last datetime the paymentTerms was modified. Read-Only.|  


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

## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 
