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

```
"ItemCategory" 
{ 
"categoryId": "String", 
"description": "String" 
} 
            
"UnitOfMeasure" 
{  
"unitCode":  "String", 
"unitName": "String", 
"symbol": "String", 
"unitConversion": "NAV.ItemUnitOfMeasureConversion" 
  } 
 
"ItemUnitOfMeasureConversion" 
{ 
"toUnitOfMeasure": "String", 
"fromToConversionRate": "Decimal" 
} 
 
"PaymentMethod" 
{ 
"code": "String", 
"description": "String" 
} 
 
"PaymentTerms" 
{ 
"code": "String", 
"description": "String" 
} 
 
"PostalAddress" 
{ 
"street": "String",
"city": "String", 
"state": "String", 
"countryLetterCode": "String", 
"postalCode": "String" 
} 
 
"ShipmentMethod" 
{ 
"code": "String", 
"description": "String" 
} 
```

## See Also
[Graph Reference](graph-reference.md)  
