---
title: "CREATETOTALS Function (Report)"
ms.custom: na
ms.date: 11/05/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: c1813dac-0e39-4538-8ca2-14431a529bbd
caps.latest.revision: 8
manager: edupont
---
# CREATETOTALS Function (Report)
Maintains totals for a variable in C/AL.  

> [!IMPORTANT]  
> This function will be deprecated in a future update and we recommend that you do not use it.
  
## Syntax  
  
```  
  
CREATETOTALS(Var1 [, Var2] ,...)  
```  
  
#### Parameters  
 *Var1*, *Var2*, …  
 Type: Decimal  
  
## Remarks  
CREATETOTALS maintains group and grand totals. The totals can be printed by placing controls that have the variable or variables that are the arguments of CREATETOTALS as their source expressions in the appropriate sections. The group totals are printed in GroupFooter sections, and the grand totals are printed in Footer sections.  
  
> [!NOTE]  
> For RDLC reports, CREATETOTALS initializes program variables, but not record fields, hence a `CREATETOTALS(MyVar)` can be replaced with or compared to `CLEAR(MyVar)` or `MyVar := 0`; 
  
## Example  
This example shows how to use the CREATETOTALS function to maintain totals for the two variables Amount and Quantity.  
  
```  
CurrReport.CREATETOTALS(Amount, Quantity);  
```  
  
## See Also  
 [Report Data Type](Report-Data-Type.md)