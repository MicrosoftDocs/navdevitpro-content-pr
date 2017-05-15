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
Represents a companyInformation resource type in Dynamics 365 for Financials.

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET companyInformation](../api/dynamics_get_companyinformation.md)|companyInformation|Get Company Information.|
|[PATCH companyInformation](../api/dynamics_update_companyinformation.md)|companyInformation|Update Company Information.|


## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the company. Read-Only.|
|displayName|string|The company's display name.|
|address|[NAV.PostalAddress](../resource_types/dynamics_complex_types.md)|The company's address. View the complex type for additional detail.|
|phoneNumber|string|The company's telephone number.|
|faxNumber|string|The company's fax number.|
|email|string|The company's email address.|
|website|string|The company's website address.|
|taxRegistrationNumber|string|The company's tax registration number.|
|currencyCode|string|The currency the company does business in. Read-Only.|
|currentFiscalYearStartDate|date|The company's current fiscal year start date. Read-Only.|
|industry|string|The industry the company is part of.|
|picture|stream|The company logo. Read-Only.|
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
  "lastModifiedDateTime": "datetime"
}

```

## See Also
[Graph Reference](../api/dynamics_graph_reference.md)  
