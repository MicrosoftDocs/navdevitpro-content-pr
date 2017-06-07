---
title: "Text Data Type"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: fe8419b7-96a2-486e-858d-51f62c66657f
caps.latest.revision: 16
---
# Text Data Type
This simple data type denotes a text string.  
  
## Remarks  
 [!INCLUDE[d365fin_md](../includes/d365fin_md.md)] does not enforce a limit on the length of a Text variable. You can specify a maximum length in the **AL Globals** or **AL Locals** window when you create the variable, but it is not required. There is no performance impact if you do not specify a length. The maximum length of a Text field in a table is 250 characters. The length of a text variable equals the number of characters in the string. An empty text string has a length of zero \(0\). A text string cannot be null.  
  
 You can index any character position in a text string, for example A[65]. The resulting value will be a [Char Data Type](Char-data-type.md).  
  
 You cannot assign a char to a position in the code variable greater than the current length of the variable +1. For more information, see [Char Data Type](Char-data-type.md).  
  
 The Text data type supports Unicode.  
  
## Example  
 This example shows some typical examples of text strings. In these examples, the text variable has a maximum length of 6.  
  
```  
text := 'ABC';  
// Results in a text variable which contains 'ABC'.  
text := '123456abc';  
// Results in a run-time error because the length (9)  
// exceeds the maximum length of 6.  
```  
  
## See Also  
 [CONVERTSTR method (Code, Text)](CONVERTSTR-method--Code--Text-.md)   
 [COPYSTR method (Code, Text)](COPYSTR-method--Code--Text-.md)   
 [DELCHR method (Code, Text)](DELCHR-method--Code--Text-.md)   
 [DELSTR method (Code, Text)](DELSTR-method--Code--Text-.md)   
 [FORMAT method (Code, Text)](FORMAT-method--Code--Text-.md)   
 [INCSTR method (Code, Text)](INCSTR-method--Code--Text-.md)   
 [INSSTR method (Code, Text)](INSSTR-method--Code--Text-.md)   
 [LOWERCASE method (Code, Text)](LOWERCASE-method--Code--Text-.md)   
 [MAXSTRLEN method (Code, Text)](MAXSTRLEN-method--Code--Text-.md)   
 [PADSTR method (Code, Text)](PADSTR-method--Code--Text-.md)   
 [SELECTSTR method (Code, Text)](SELECTSTR-method--Code--Text-.md)   
 [STRCHECKSUM method (Code, Text)](STRCHECKSUM-method--Code--Text-.md)   
 [STRLEN method (Code, Text)](STRLEN-method--Code--Text-.md)   
 [STRPOS method (Code, Text)](STRPOS-method--Code--Text-.md)   
 [STRSUBSTNO method (Code, Text)](STRSUBSTNO-method--Code--Text-.md)   
 [UPPERCASE method (Code, Text)](UPPERCASE-method--Code--Text-.md)