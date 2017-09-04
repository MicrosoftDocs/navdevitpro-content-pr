---
title: companyInformation resource type | Microsoft Docs
description: Company Information.
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

# companyInformation resource type
Represents the information specified for the current company in Dynamics 365 for Financials, such as name, address, email address, and website address.

## Methods

| Method         | Return Type  |Description|
|:---------------|:-------------|:----------|
|[GET companyInformation](../api/dynamics_get_companyinformation.md)|companyInformation|Get Company Information.|
|[PATCH companyInformation](../api/dynamics_update_companyinformation.md)|companyInformation|Update Company Information.|


## Properties
| Property	   | Type	   |Description                           |
|:-------------|:--------|:-------------------------------------|
|id            |GUID|The unique ID of the company. Non-editable.|
|displayName   |string   |The company's display name.           |
|address       |[NAV.PostalAddress](../resources/dynamics_complex_types.md)|The company's address. View the complex type for additional detail.|
|phoneNumber   |string   |The company's telephone number.       |
|faxNumber     |string   |The company's fax number.             |
|email         |string   |The company's email address.          |
|website       |string   |The company's website address.        |
|taxRegistrationNumber|string|The company's tax registration number.|
|currencyCode  |string   |The currency the company does business in. Read-Only.|
|currentFiscalYearStartDate|date|The company's current fiscal year start date. Read-Only.|
|industry      |string   |The industry the company is part of.  |
|picture       |stream   |The company logo. Read-Only.          |
|businessProfileId|string|The business profile ID linked to the Financials company. Read-Only.|
|lastModifiedDateTime|datetime|The last datetime the company was modified. Read-Only.|  


## Relationships
None

## JSON representation

Here is a JSON representation of the companyInformation
```json
{
  "id": "GUID",
  "displayName": "string",
  "address": "NAV.PostalAddress",
  "phoneNumber": "string",
  "faxNumber": "string",
  "email": "string",
  "website": "string",
  "taxRegistrationNumber": "string",
  "currencyCode": "string",
  "currentFiscalYearStartDate": "date",
  "industry": "string",
  "picture": "stream",
  "businessProfileId": "string",
  "lastModifiedDateTime": "datetime"
}

```

## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 
