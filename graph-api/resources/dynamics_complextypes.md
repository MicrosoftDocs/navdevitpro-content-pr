---
title: complex types JSON | Microsoft Docs
description: Complex data types in JSON for Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/19/2018
ms.author: solsen
---

# complex types JSON
These are the various complex types in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)]. You can see usage of these complex types in the various individual methods that make use of them.

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see .

## Postal address

Represents a Postal Address complex type in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].       

### Properties
| Property	   | Type	    |Description             |
|:-------------|:---------|:-----------------------|
|street        |string    |Postal address street.  |
|city          |string    |Postal address city.    |
|state         |string    |Postal address state.   |
|countryLetterCode|string |Postal address country letter code (two character word)|
|postalCode    |string    |Postal address post code|

```json
"PostalAddress" 
{ 
"street": "string",
"city": "string", 
"state": "string", 
"countryLetterCode": "string", 
"postalCode": "string" 
} 
 ```

## See also
[Working with Dynamics 365 Business Central in Microsoft Graph](../resources/dynamics_overview.md)  
[Error Codes](../dynamics_error_codes.md)  
