---
title: Get configurationPackage | Microsoft Docs
description: Gets a configurationPackage object in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: henrikwh

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/19/2018
ms.author: solsen
---

# Get configurationPackage
Retrieve the properties and relationships of an configurationPackage object for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## Bound Actions

| Actions         | Return Type  |Description|
|:---------------|:-------------|:----------|
|[Microsoft.NAV.import](../api/dynamics_microsoft_automation_extension_post.md)|none|Imports a configurationPackage.|
|[Microsoft.NAV.apply](../api/dynamics_microsoft_automation_extension_post.md)|extension|Applies a configurationPackage.|

## HTTP requests
### Insert configurationPackage
```json
POST /microsoft/automation/{apiVersion}/companies({companyId})/configurationPackages
Content-type: application/json
{
    "code":"YourPackageName"
}
```

### Import configurationPackage
```json
POST /microsoft/automation/{apiVersion}/companies({companyId})/configurationPackages('{packageName}')/Microsoft.NAV.import

```
### Apply configurationPackage
```json
POST /microsoft/automation/{apiVersion}/companies({companyId})/configurationPackages('{packageName}')/Microsoft.NAV.apply

```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code.

## Example

**Request**

Here is an example of the request.
```json
GET https://api.businesscentral.dynamics.com/v1.0/api/microsoft/automation/beta/companies({companyId})/configurationPackages('{packageName}')/Microsoft.NAV.import
```

**Response**

Here is an example of the response. 

> [!NOTE]  
>   The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
    "code": "RAS2",
    "packageName": "SAMPLE",
    "languageId": 0,
    "productVersion": "",
    "processingOrder": 0,
    "excludeConfigurationTables": false,
    "numberOfTables": 12,
    "numberOfRecords": 3,
    "numberOfErrors": 3,
    "importStatus": "Completed",
    "applyStatus": "Completed"
}
```

## See Also
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[ConfigurationPackage entity](../resources/dynamics_microsoft_automation_configurationPackages.md)  
