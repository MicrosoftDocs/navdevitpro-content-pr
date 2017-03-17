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
ms.date: 02/08/2017
ms.author: solsen
---

# companyInformation resource type

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|Get companyInformation|companyInformation|Get a companyInformation object.|
|Update companyInformation|companyInformation|Update a companyInformation object.|


## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the companyInformation. Read-Only.|
|displayName|string|The companyInformation's display name.|
|address|NAV.PostalAddress|The companyInformation's address.|
|phoneNumber|string|The companyInformation's telephone number.|
|faxNumber|string|The companyInformation's fax number.|
|email|string|The companyInformation's email address.|
|website|string|The companyInformation's website address.|
|taxRegistrationNumber|string|The companyInformation's tax registration number.|
|currencyCode|string|The currency the company does business in. Read-Only.|
|currentFiscalYearStartDate|date|The companies current fiscal year start date. Read-Only.|
|industry|string|The industry the company is part of.|
|picture|stream|The company logo. Read-Only.|
|lastModifiedDateTime|datetime|The last datetime the companyInformation was modified. Read-Only.|  


## Relationships
None

## JSON representation

Here is a JSON representation of the vendor.


```
{
  "displayName": "string",
  "address": {NAV.PostalAddress},
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