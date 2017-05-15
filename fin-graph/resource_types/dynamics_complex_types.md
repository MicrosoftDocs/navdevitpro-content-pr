---
title: Complex Types JSON | Microsoft Docs
description: Complex data types JSON.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/16/2017
ms.author: solsen
---

# Complex Types JSON
These are the various complex types in Dynamics 365 for Financials. You can see usage of these complex types in the various individual methods that make use of them.

# Item Category

Represents an Item Category complex type in Dynamics 365 for Financials.
```json
"ItemCategory" 
{ 
  "categoryId": "string", 
  "description": "string" 
} 
```

# Unit of Measure

Represents a Unit of Measure complex type in Dynamics 365 for Financials.       
```json
"UnitOfMeasure" 
{  
  "unitCode":  "string", 
  "unitName": "string", 
  "symbol": "string", 
  "unitConversion": "NAV.ItemUnitOfMeasureConversion" 
} 
```

# Unit of Measure Conversion

Represents a Unit of Measure Conversion complex type in Dynamics 365 for Financials.       
```json
"ItemUnitOfMeasureConversion" 
{ 
"toUnitOfMeasure": "string", 
"fromToConversionRate": "decimal" 
} 
 ```

 # Payment Method

Represents a Payment Method complex type in Dynamics 365 for Financials.       

```json
"PaymentMethod" 
{ 
"code": "string", 
"description": "string" 
} 
 ```

 # Payment Terms

Represents a Payment Terms complex type in Dynamics 365 for Financials.       
```json
"PaymentTermsType" 
{ 
"code": "string", 
"description": "string" 
} 
 ```

 # Postal Address

Represents a Postal Address complex type in Dynamics 365 for Financials.       
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

 # Shipment Method

Represents a Shipment Method complex type in Dynamics 365 for Financials.       
```json
"ShipmentMethod" 
{ 
"code": "string", 
"description": "string" 
} 
```

# Line Details

Represents a Line Details complex type in Dynamics 365 for Financials.       
```json
"documentLineObjectDetails" 
{ 
"number": "string", 
"displayName": "string" 
"description": "string" 
} 
```

## See Also
[Graph Reference](../api/dynamics_graph_reference.md)  
