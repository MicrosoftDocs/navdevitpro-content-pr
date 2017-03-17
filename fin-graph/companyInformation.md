---
title: Company Information resource type | Microsoft Docs
description: Company Information.
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

# Company Information resource type

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET companyInformation](get-companyInformation.md)|companyInformation|Get a companyInformation object.|
|[Update companyInformation](update-companyInformation.md)|companyInformation|Update a companyInformation object.|


## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the Company. Read-Only.|
|displayName|string|The Company's display name.|
|address|[NAV.PostalAddress](complex-types.md)|The Company's address. View the complex type for additional detail.|
|phoneNumber|string|The Company's telephone number.|
|faxNumber|string|The Company's fax number.|
|email|string|The Company's email address.|
|website|string|The Company's website address.|
|taxRegistrationNumber|string|The Company's tax registration number.|
|currencyCode|string|The currency the Company does business in. Read-Only.|
|currentFiscalYearStartDate|date|The Company's current fiscal year start date. Read-Only.|
|industry|string|The industry the Company is part of.|
|picture|stream|The Company logo. Read-Only.|
|lastModifiedDateTime|datetime|The last datetime the Company was modified. Read-Only.|  


## Relationships
None

## JSON representation

Here is a JSON representation of the companyInformation
```json
{
  "id": "GUID",
  "displayName": "string",
  "address": NAV.PostalAddress,
  "phoneNumber": "string",
  "faxNumber": "string",
  "email": "string",
  "website": "string",
  "taxRegistrationNumber": "string",
  "currencyCode": "string",
  "currentFiscalYearStartDate": "date",
  "industry": "string",
  "picture": "stream",
  "lastModifiedDateTime": "datetime"
}

```

## See Also
[Graph Reference](graph-reference.md)  