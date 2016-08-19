---
title: "COUNT Function (FilterPageBuilder)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: ae7d1b03-4a3b-4cc5-b76f-ef8875dfe5b5
caps.latest.revision: 3
manager: edupont
---
# COUNT Function (FilterPageBuilder)
Gets the number of filter controls that are specified in the FilterPageBuilder object instance.  
  
## Syntax  
  
```  
  
Count := FilterPageBuilder.COUNT  
```  
  
## Return Value  
 Type: Integer  
  
 The number of filter controls in the current FilterPageBuilder object instance.  
  
## Example  
 The following example uses the COUNT function on a filter page object that includes a two filter controls for the **Date** system table.  
  
 This example requires that you create the following variables in the **C\/AL Globals** window.  
  
|Variable name|DataType|SubType|  
|-------------------|--------------|-------------|  
|varDateItem|Text||  
|varCount|Integer|Date|  
|varFilterPageBuilder|FilterPageBuilder||  
  
```  
varDateItem := 'Date record';  
varFilterPageBuilder.ADDTABLE(varDateItem + ‘ 1’,DATABASE::Date);  
varFilterPageBuilder.ADDTABLE(varDateItem + ‘ 2’,DATABASE::Date);  
varCount := varFilterPageBuilder.COUNT;  
IF varCount <> 2 THEN   
  ERROR(‘There should be two controls in varFilterPageBuilder’);  
```  
  
## See Also  
 [ADDFIELD Function](../dynamics-nav/ADDFIELD-Function.md)   
 [ADDFIELDNO Function](../dynamics-nav/ADDFIELDNO-Function.md)   
 [ADDRECORD Function](../dynamics-nav/ADDRECORD-Function.md)   
 [ADDRECORDREF Function](../dynamics-nav/ADDRECORDREF-Function.md)   
 [ADDTABLE Function](../dynamics-nav/ADDTABLE-Function.md)   
 [GETVIEW function \(FilterPageBuilder\)](../dynamics-nav/GETVIEW-function--FilterPageBuilder-.md)   
 [SETVIEW Function](../dynamics-nav/SETVIEW-Function.md)   
 [NAME Function \(FilterPageBuilder\)](../dynamics-nav/NAME-Function--FilterPageBuilder-.md)   
 [RUNMODAL Function \(FilterPageBuilder\)](../dynamics-nav/RUNMODAL-Function--FilterPageBuilder-.md)