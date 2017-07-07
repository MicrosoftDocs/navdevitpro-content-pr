---
title: "Text Data Type"
description: 
author: SusanneWindfeldPedersen

ms.custom: na
ms.date: 07/07/2017
ms.author: solsen
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
 [!INCLUDE[d365fin_md](../includes/d365fin_md.md)] does not enforce a limit on the length of a Text variable. You can specify a maximum length in the **AL Globals** or **AL Locals** window when you create the variable, but it is not required. There is no performance impact if you do not specify a length. The maximum length of a Text field in a table is 250 characters. The length of a text variable equals the number of characters in the string. An empty text string has a length of zero (0). A text string cannot be null.  
  
 You can index any character position in a text string, for example A[65]. The resulting value will be a [Char Data Type](devenv-char-data-type.md).  
  
 You cannot assign a char to a position in the code variable greater than the current length of the variable +1. For more information, see [Char Data Type](devenv-char-data-type.md).  
  
 The Text data type supports Unicode.  

## Methods
The following methods are supported for the Text data type:

[CONVERTSTR method (Code, Text)](../methods/devenv-convertstr-method-code-text.md)   
[COPYSTR method (Code, Text)](../methods/devenv-copystr-method-code-text.md)   
[DELCHR method (Code, Text)](../methods/devenv-delchr-method-code-text.md)   
[DELSTR method (Code, Text)](../methods/devenv-delstr-method-code-text.md)   
[FORMAT method (Code, Text)](../methods/devenv-format-method-code-text.md)   
[INCSTR method (Code, Text)](../methods/devenv-incstr-method-code-text.md)   
[INSSTR method (Code, Text)](../methods/devenv-insstr-method-code-text.md)   
[LOWERCASE method (Code, Text)](../methods/devenv-lowercase-method-code-text.md)   
[MAXSTRLEN method (Code, Text)](../methods/devenv-maxstrlen-method-code-text.md)   
[PADSTR method (Code, Text)](../methods/devenv-padstr-method-code-text.md)   
[SELECTSTR method (Code, Text)](../methods/devenv-selectstr-method-code-text.md)   
[STRCHECKSUM method (Code, Text)](../methods/devenv-strchecksum-method-code-text.md)   
[STRLEN method (Code, Text)](../methods/devenv-strlen-method-code-text.md)   
[STRPOS method (Code, Text)](../methods/devenv-strpos-method-code-text.md)   
[STRSUBSTNO method (Code, Text)](../methods/devenv-strsubstno-method-code-text.md)   
[UPPERCASE method (Code, Text)](../methods/devenv-uppercase-method-code-text.md)

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
[AL Data Types](devenv-al-data-types.md)  