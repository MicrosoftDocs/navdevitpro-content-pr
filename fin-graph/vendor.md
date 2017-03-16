---
title: vendor resource type | Microsoft Docs
description: A vendor.
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

# vendor resource type

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|Get vendor|vendor|Get a vendor object.|
|Create vendor|vendor|Create a vendor object.|
|Update vendor|vendor|Update a vendor object.|
|Delete vendor|none|Delete a vendor object.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the vendor. Read-Only.|
|number|string|The vendor number.|
|displayName|string|The vendor's display name.|
|address|NAV.PostalAddress|The vendor's address.|
|phoneNumber|string|The vendor's telephone number.|
|email|string|The vendor's email address.|
|website|string|The vendor's website address.|
|taxRegistrationNumber|string|The vendor's tax registration number.|
|currencyCode|string|The default currency code for the vendor.|
|irs1099Code|string|Specifies a 1099 code for the vendor. US tenants only, blank for other countries.|
|paymentTerms|NAV.PaymentTerms|The default payment terms for the vendor.|
|paymentMethod|NAV.PaymentMethod|The default payment method for the vendor.|
|taxLiable|boolean|Specifies if the vendor is liable for tax.|
|blocked|string|Specifies which transactions with the vendor that cannot be posted. Accepted values are blank, Payment or All|
|balance|decimal|The vendor's balance. Read-Only.|
|lastModifiedDateTime|datetime|The last datetime the vendor was modified. Read-Only.|  


## Relationships
None

## JSON representation

Here is a JSON representation of the vendor.


```
{
  "number": "string",
  "displayName": "string",
  "address": {NAV.PostalAddress},
  "phoneNumber": "string",
  "email": "string",
  "website": "string",
  "taxRegistrationNumber": "string",
  "currencyCode": "string",
  "irs1099Code": "string",
  "paymentTerms": {NAV.PaymentTermsType},
  "paymentMethod": {NAV.PaymentMethod},
  "taxLiable": "boolean",
  "blocked": "string",
  "balance": "decimal",
  "lastModifiedDateTime": "datetime"
}

```

## See Also
[Graph Reference](graph-reference.md)  
