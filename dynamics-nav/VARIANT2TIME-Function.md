---
title: "VARIANT2TIME Function"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 2fa5fb1e-998c-4469-bd90-2ed0f64190fe
caps.latest.revision: 10
manager: terryaus
---
# VARIANT2TIME Function
Gets a time from a variant.  
  
## Syntax  
  
```  
  
Time := VARIANT2TIME(Variant)  
```  
  
#### Parameters  
 *Variant*  
 Type: Variant  
  
 The input variant.  
  
## Property Value\/Return Value  
 Type: Time  
  
 The resulting time.  
  
## Example  
 This example requires that you create the following variables.  
  
|Name|DataType|  
|----------|--------------|  
|TestTime|Time|  
|variant1|Variant|  
  
```  
variant1 := TIME;  
TestTime := VARIANT2TIME(variant1);  
```  
  
## See Also  
 [Variant Data Type](../dynamics-nav/Variant-Data-Type.md)   
 [Date and Time Functions](../dynamics-nav/Date-and-Time-Functions.md)   
 [Using COM Technologies in Microsoft Dynamics NAV](../dynamics-nav/Using-COM-Technologies-in-Microsoft-Dynamics-NAV.md)