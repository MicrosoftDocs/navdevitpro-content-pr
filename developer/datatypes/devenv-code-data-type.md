---
title: "Code Data Type"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 5f0c3922-cf78-49a1-9143-466bffa29ab3
caps.latest.revision: 21
manager: edupont
---
# Code Data Type
This simple data type denotes a special type of string that is converted to uppercase and removes any trailing or leading spaces.  
  
## Remarks  
 The length of a Code variable equals the number of characters in the text without leading or trailing spaces.  
  
 You must specify the length of a Code variable or field. The maximum length of a Code variable is 1024 characters. The maximum length of a Code field in a table is 250 characters.  
  
 A Code variable cannot be null.  
  
 The Code data type supports Unicode.  
  
 You can index any character position in a string, such as A\[65\]. The resulting value will be a [Char Data Type](Char-data-type.md).  
  
 Fields that contain a date formula must not have data type Code. Instead, use the [DateFormula Data Type](DateFormula-data-type.md). All fields that contain a date formula with data type Code must be converted into data type DateFormula.  
  
 You cannot assign a char to a position in the code variable greater than the current length of the variable +1. For more information, see [Char Data Type](Char-data-type.md).  
  
## Example  
 This example shows some typical examples of code string assignments. In these examples, assume that the variable c is a code variable with a maximum length of 4.  
  
```  
c := 'ABC';   
// Results in variable c, which contains 'ABC'   
// and is 3 characters in length.  
c := '1';  
// Results in variable c, which contains '1'   
// and is 1 character in length.  
c := '';  
// Results in variable c, which contains '' (empty string)  
// and is zero (0) characters in length.  
c := ' 2 ';  
// Results in variable c, which contains '2'  
// and is 1 character in length.  
```  
  
## See Also  
 [CONVERTSTR method \(Code, Text\)](CONVERTSTR-method--Code--Text-.md)   
 [COPYSTR method \(Code, Text\)](COPYSTR-method--Code--Text-.md)   
 [DELCHR method \(Code, Text\)](DELCHR-method--Code--Text-.md)   
 [DELSTR method \(Code, Text\)](DELSTR-method--Code--Text-.md)   
 [FORMAT method \(Code, Text\)](FORMAT-method--Code--Text-.md)   
 [INCSTR method \(Code, Text\)](INCSTR-method--Code--Text-.md)   
 [INSSTR method \(Code, Text\)](INSSTR-method--Code--Text-.md)   
 [LOWERCASE method \(Code, Text\)](LOWERCASE-method--Code--Text-.md)   
 [MAXSTRLEN method \(Code, Text\)](MAXSTRLEN-method--Code--Text-.md)   
 [PADSTR method \(Code, Text\)](PADSTR-method--Code--Text-.md)   
 [SELECTSTR method \(Code, Text\)](SELECTSTR-method--Code--Text-.md)   
 [STRCHECKSUM method \(Code, Text\)](STRCHECKSUM-method--Code--Text-.md)   
 [STRLEN method \(Code, Text\)](STRLEN-method--Code--Text-.md)   
 [STRPOS method \(Code, Text\)](STRPOS-method--Code--Text-.md)   
 [STRSUBSTNO method \(Code, Text\)](STRSUBSTNO-method--Code--Text-.md)   
 [UPPERCASE method \(Code, Text\)](UPPERCASE-method--Code--Text-.md)