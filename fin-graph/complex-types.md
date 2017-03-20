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

```json
"ItemCategory" 
{ 
"categoryId": "string", 
"description": "string" 
} 
            
"UnitOfMeasure" 
{  
"unitCode":  "string", 
"unitName": "string", 
"symbol": "string", 
"unitConversion": "NAV.ItemUnitOfMeasureConversion" 
  } 
 
"ItemUnitOfMeasureConversion" 
{ 
"toUnitOfMeasure": "string", 
"fromToConversionRate": "decimal" 
} 
 
"PaymentMethod" 
{ 
"code": "string", 
"description": "string" 
} 
 
"PaymentTerms" 
{ 
"code": "string", 
"description": "string" 
} 
 
"PostalAddress" 
{ 
"street": "string",
"city": "string", 
"state": "string", 
"countryLetterCode": "string", 
"postalCode": "string" 
} 
 
"ShipmentMethod" 
{ 
"code": "string", 
"description": "string" 
} 
```

## See Also
[Graph Reference](graph-reference.md)  
