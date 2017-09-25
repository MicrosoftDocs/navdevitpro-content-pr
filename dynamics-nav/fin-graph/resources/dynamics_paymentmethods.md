---
title: paymentMethods resource type | Microsoft Docs
description: A payment method object in Dynamics 365 for Financials.
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

# paymentMethods resource type
Represents a method of payment in Dynamics 365 for Financials, such as PayPal, credit card, and bank account.

## Methods

| Method                                                          | Return Type  |Description             |
|:----------------------------------------------------------------|:-------------|:-----------------------|
|[GET paymentMethods](../api/dynamics_get_paymentmethods.md)      |paymentMethods|Get a Payment Method.   |
|[POST paymentMethods](../api/dynamics_create_paymentmethods.md)  |paymentMethods|Create a Payment Method.|
|[PATCH paymentMethods](../api/dynamics_update_paymentmethods.md) |paymentMethods|Update a Payment Method.|
|[DELETE paymentMethods](../api/dynamics_delete_paymentmethods.md)|none          |Delete a Payment Method.|

## Properties
| Property	         | Type	  |Description                                                  |
|:-------------------|:-------|:------------------------------------------------------------|
|id                  |GUID    |The unique ID of the paymentMethods. Non-editable.           |
|code                |string  |Specifies the payment method code.                           |
|displayName         |string  |Specifies the payment method display name.                   |
|lastModifiedDateTime|datetime|The last datetime the payment method was modified. Read-Only.|  


## Relationships
None

## JSON representation

Here is a JSON representation of the paymentMethods.


```json
{
  "id": "GUID",
  "code": "string",
  "displayName": "string",
  "lastModifiedDateTime": "datetime"
}

```

## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 
