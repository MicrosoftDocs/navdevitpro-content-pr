---
title: "ISFILTERPAGEBUILDER Function (Variant)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 633646e7-72d6-4aab-a2f0-e8d4c561d37e
caps.latest.revision: 2
manager: edupont
---
# ISFILTERPAGEBUILDER Function (Variant)
Indicates whether a C\/AL variant contains a FilterPageBuilder variable.  
  
## Syntax  
  
```  
Ok := Variant.ISFILTERPAGEBUILDER  
```  
  
#### Parameters  
 Type: Variant  
  
## Return Value  
 Type: Boolean  
  
 **true** if the C\/AL variant contains a FilterPageBuilder variable; otherwise, **false**.  
  
## Example  
 The following example uses the ISFILTERPAGEBUILDER function on a filter page object that includes a filter control for the **Date** system table.  
  
 This example requires that you create the following variables in the **C\/AL Globals** window.  
  
|Variable name|DataType|SubType|  
|-------------------|--------------|-------------|  
|varDateItem|Text||  
|varFilterPageBuilder|FilterPageBuilder||  
|myVariant|Variant||  
  
```  
varDateItem := 'Date record';  
varFilterPageBuilder.ADDTABLE(varDateItem + ‘ 1’,DATABASE::Date);  
myVariant := varFilterPageBuilder;  
IF not myVariant.ISFILTERPAGEBUILDER THEN   
  ERROR(‘This variant should contain a FilterPageBuilder variable’);  
  
```  
  
## See Also  
 [Variant Data Type](../dynamics-nav/Variant-Data-Type.md)   
 [FilterPageBuilder Data Type](../dynamics-nav/FilterPageBuilder-Data-Type.md)   
 [ADDFIELD Function](../dynamics-nav/ADDFIELD-Function.md)   
 [ADDFIELDNO Function](../dynamics-nav/ADDFIELDNO-Function.md)   
 [ADDRECORD Function](../dynamics-nav/ADDRECORD-Function.md)   
 [ADDRECORDREF Function](../dynamics-nav/ADDRECORDREF-Function.md)   
 [ADDTABLE Function](../dynamics-nav/ADDTABLE-Function.md)   
 [GETVIEW function \(FilterPageBuilder\)](../dynamics-nav/GETVIEW-function--FilterPageBuilder-.md)   
 [SETVIEW Function](../dynamics-nav/SETVIEW-Function.md)   
 [COUNT Function \(FilterPageBuilder\)](../dynamics-nav/COUNT-Function--FilterPageBuilder-.md)   
 [NAME Function \(FilterPageBuilder\)](../dynamics-nav/NAME-Function--FilterPageBuilder-.md)   
 [RUNMODAL Function \(FilterPageBuilder\)](../dynamics-nav/RUNMODAL-Function--FilterPageBuilder-.md)