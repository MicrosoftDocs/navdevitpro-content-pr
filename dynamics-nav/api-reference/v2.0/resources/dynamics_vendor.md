---
title: vendor resource type | Microsoft Docs
description: A vendor object in Dynamics 365 Business Central. 
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# vendor resource type
Represents a vendor in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET vendor](../api/dynamics_vendor_get.md)|vendor|Gets a vendor object.|
|[POST vendor](../api/dynamics_create_vendor.md)|vendor|Creates a vendor object.|
|[PATCH vendor](../api/dynamics_vendor_update.md)|vendor|Updates a vendor object.|
|[DELETE vendor](../api/dynamics_vendor_delete.md)|none|Deletes a vendor object.|



## Navigation

| Navigation |Return Type| Description |
|:----------|:----------|:-----------------|
|[countryRegion](../resources/dynamics_countryregion.md)|countryRegion   |Gets the countryregion of the vendor.|
|[currency](../resources/dynamics_currency.md)|currency   |Gets the currency of the vendor.|
|[paymentTerm](../resources/dynamics_paymentterm.md)|paymentTerm   |Gets the paymentterm of the vendor.|
|[paymentMethod](../resources/dynamics_paymentmethod.md)|paymentMethod   |Gets the paymentmethod of the vendor.|
|[picture](../resources/dynamics_picture.md)|picture   |Gets the picture of the vendor.|
|[defaultDimensions](../resources/dynamics_defaultdimensions.md)|defaultDimensions   |Gets the defaultdimensions of the vendor.|
|[agedAccountsPayable](../resources/dynamics_agedaccountspayable.md)|agedAccountsPayable   |Gets the agedaccountspayable of the vendor.|

## Properties

| Property     | Type   |Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the vendor. Non-editable.|
|number|string|The vendor number.|
|displayName|string|The vendor's display name.|
|address|[NAV.PostalAddress](../resources/dynamics_complextypes.md)|The vendor's address.|
|phoneNumber|string|The vendor's telephone number.|
|email|string|The vendor's email address.|
|website|string|The vendor's website address.|
|taxRegistrationNumber|string|The vendor's tax registration number.|
|currencyId|GUID|The default currency code ID for the vendor.|
|currencyCode|string|The default currency code for the vendor.|
|irs1099Code|string|Specifies a 1099 code for the vendor. US only.|
|paymentTermsId|GUID|The default payment terms ID for the vendor.|
|paymentMethodId|GUID|The default payment method ID for the vendor.|
|taxLiable|boolean|Specifies if the vendor is liable for tax.|
|blocked|string|Specifies which transactions with the vendor that cannot be posted. Accepted values are blank, Payment or All|
|balance|decimal|The vendor's balance. Read-Only.|
|lastModifiedDateTime|datetime|The last datetime the vendor was modified. Read-Only.|  


## JSON representation

Here is a JSON representation of the vendor.

```json
{
   "id": "GUID",
   "number": "string",
   "displayName": "string",
   "addressLine1": "string",
   "addressLine2": "string",
   "city": "string",
   "state": "string",
   "country": "string",
   "postalCode": "string",
   "phoneNumber": "string",
   "email": "string",
   "website": "string",
   "taxRegistrationNumber": "string",
   "currencyId": "GUID",
   "currencyCode": "string",
   "irs1099Code": "string",
   "paymentTermsId": "GUID",
   "paymentMethodId": "GUID",
   "taxLiable": "boolean",
   "blocked": "boolean",
   "balance": "decimal",
   "lastModifiedDateTime": "datetime"
}
```

## See also

[Get Vendor](../api/dynamics_vendor_get.md)  
[Create Vendor](../api/dynamics_create_vendor.md)  
[Update Vendor](../api/dynamics_vendor_update.md)  
[Delete Vendor](../api/dynamics_vendor_delete.md)  