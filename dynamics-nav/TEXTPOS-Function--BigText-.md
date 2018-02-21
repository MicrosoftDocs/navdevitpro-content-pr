---
title: "TEXTPOS Function (BigText)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 46b5a4a6-4c1e-472e-8092-e92032e521a9
caps.latest.revision: 16
---
# TEXTPOS Function (BigText)
Gets the position at which a specific string first occurs in a BigText.  
  
## Syntax  
  
```  
  
Position := BigText.TEXTPOS(String)  
```  
  
#### Parameters  
 *String*  
 Type: Text  
  
 The text string to search for in the **BigText** variable. If this parameter is empty, then 0 is returned.  
  
## Property Value/Return Value  
 Type: Integer  
  
 This return value indicates the position where the first occurrence of the string starts in the *BigText* variable.  
  
 If *String* is not found in the *BigText* variable, then 0 is returned.  
  
## Remarks  
 The first character in a *BigText* variable is position 1.  
  
## Example  
 The following examples show how to use the TEXTPOS function. These examples require that you create the following variables and text constant in the **C/AL Globals** window.  
  
|Variable name|DataType|  
|-------------------|--------------|  
|MyBigText|BigText|  
|VarPosition|Integer|  
  
|Text constant name|ENU value|  
|------------------------|---------------|  
|Text000|VarPosition = %1|  
  
 The following examples first initialize the content of the *BigText* variable with the text `ABCDEFG`.  
  
 In this example, the first occurrence of the character B \(the first character of the specified text\) is found in the second position in the MyBigText variable so the function returns 2. The return value is stored in the variable VarPosition and displayed in a message box.  
  
```  
MyBigText.ADDTEXT('ABCDEFG');  
VarPosition := MyBigText.TEXTPOS('BCD'); // Returns 2.  
MESSAGE(Text000, VarPosition);  
  
```  
  
## Example  
 In the following example, the function returns 0 because the specified string is not found in the MyBigText variable. The return value is stored in the variable VarPosition and displayed in a message box.  
  
```  
MyBigText.ADDTEXT('ABCDEFG');  
VarPosition := MyBigText.TEXTPOS(''); // Returns 0.  
MESSAGE(Text000, VarPosition);  
```  
  
## Example  
 In the following example, the function returns 0 because the specified string is not found in the MyBigText variable. The return value is stored in the variable VarPosition and displayed in a message box.  
  
```  
MyBigText.ADDTEXT('ABCDEFG');  
VarPosition := MyBigText.TEXTPOS('XYZ'); // Returns 0.  
MESSAGE(Text000, VarPosition);  
```  
  
## See Also  
 [BigText Data Type](BigText-Data-Type.md)   
 [BigText Functions](BigText-Functions.md)