---
title: "OPTIONCAPTION Function (FieldRef)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 10d59dd6-b479-45be-95ca-5cef870e7e42
caps.latest.revision: 12
---
# OPTIONCAPTION Function (FieldRef)
Gets the option caption of the field that is currently selected.  
  
## Syntax  
  
```  
  
OptionCaption := FieldRef.OPTIONCAPTION  
```  
  
#### Parameters  
 *FieldRef*  
 Type: FieldRef  
  
 Refers to the current field.  
  
## Property Value/Return Value  
 Type: Text  
  
 The option caption of the field.  
  
## Remarks  
 The option caption of the field is returned as a comma separated string.  
  
 If the field is not an Option, an empty string is returned.  
  
 This function returns an error if no field is selected.  
  
## Example  
 The following example opens the Item table as a RecordRef variable that is named ItemRecref. and creates a reference to field 19 \(Price/Profit Calculation field\), which is an Option field. The OPTIONCAPTION function retrieves the caption of the option field and displays the options as a comma separated list. This example requires that you create the following variables in the **C/AL Globals** windows.  
  
|Variable name|DataType|  
|-------------------|--------------|  
|ItemRecref|RecordRef|  
|MyFieldRef|FieldRef|  
|OptionCaption|Text|  
  
```  
  
ItemRecref.OPEN(DATABASE::Item);  
MyFieldRef := ItemRecref.FIELD(19);  
OptionCaption := MyFieldRef.OPTIONCAPTION;  
MESSAGE('%1', OptionCaption);  
```  
  
## See Also  
 [FieldRef Data Type](FieldRef-Data-Type.md)