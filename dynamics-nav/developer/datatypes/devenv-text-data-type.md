---
title: "Text Data Type"
ms.custom: na
ms.date: 07/20/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: fe8419b7-96a2-486e-858d-51f62c66657f
caps.latest.revision: 16
author: SusanneWindfeldPedersen
---
# Text Data Type
This simple data type denotes a text string.  
  
## Remarks  
 [!INCLUDE[d365fin_md](../includes/d365fin_md.md)] does not enforce a limit on the length of a Text variable. You can specify a maximum length in the **AL Globals** or **AL Locals** window when you create the variable, but it is not required. There is no performance impact if you do not specify a length. The maximum length of a Text field in a table is 250 characters. The length of a text variable equals the number of characters in the string. An empty text string has a length of zero (0). A text string cannot be null.  
  
 You can index any character position in a text string, for example A[65]. The resulting value will be a [Char Data Type](devenv-char-data-type.md).  
  
 You cannot assign a char to a position in the code variable greater than the current length of the variable +1. For more information, see [Char Data Type](devenv-char-data-type.md).  
  
 The Text data type supports Unicode.  

## Methods
  
The following methods are supported for *instance* Text data type:  

|Method      |Instance   |
|------------|-----------|
|[CONTAINS Method (Text)](../methods/devenv-contains-method-text.md)|X|
|[ENDSWITH Method (Text)](../methods/devenv-endswith-method-text.md)|X|
|[INDEXOFANY Method (Text)](../methods/devenv-indexofany-method-text.md)|X|
|[INDEXOF Method (Text)](../methods/devenv-indexof-method-text.md)|X|
|[LASTINDEXOF Method (Text)](../methods/devenv-lastindexof-method-text.md)|X|
|[PADLEFT Method (Text)](../methods/devenv-padleft-method-text.md)|X|
|[PADRIGHT Method (Text)](../methods/devenv-padright-method-text.md)|X|
|[REMOVE Method (Text)](../methods/devenv-remove-method-text.md)|X|
|[REPLACE Method (Text)](../methods/devenv-replace-method-text.md)|X|
|[STARTSWITH Method (Text)](../methods/devenv-startswith-method-text.md)|X|
|[SUBSTRING Method (Text)](../methods/devenv-substring-method-text.md)|X|
|[TOLOWER Method (Text)](../methods/devenv-tolower-method-text.md)|X|
|[TOUPPER Method (Text)](../methods/devenv-toupper-method-text.md)|X|
|[TRIMEND Method (Text)](../methods/devenv-trimend-method-text.md)|X|
|[TRIM Method (Text)](../methods/devenv-trim-method-text.md)|X|
|[TRIMSTART Method (Text)](../methods/devenv-trimstart-method-text.md)|X|

The following methods are supported for the *static* Text data type:

|Method       |Static    |
|------------|-----------|
|[CONVERTSTR Method (Code, Text)](../methods/devenv-convertstr-method-code-text.md)|X|
|[COPYSTR Method (Code, Text)](../methods/devenv-copystr-method-code-text.md)|X|
|[DELCHR Method (Code, Text)](../methods/devenv-delchr-method-code-text.md)|X|
|[DELSTR Method (Code, Text)](../methods/devenv-delstr-method-code-text.md)|X| 
|[FORMAT Method (Code, Text)](../methods/devenv-format-method-code-text.md)|X|
|[INCSTR Method (Code, Text)](../methods/devenv-incstr-method-code-text.md)|X|
|[INSSTR Method (Code, Text)](../methods/devenv-insstr-method-code-text.md)|X|
|[LOWERCASE Method (Code, Text)](../methods/devenv-lowercase-method-code-text.md)|X|
|[MAXSTRLEN Method (Code, Text)](../methods/devenv-maxstrlen-method-code-text.md)|X|
|[PADSTR Method (Code, Text)](../methods/devenv-padstr-method-code-text.md)|X|
|[SELECTSTR Method (Code, Text)](../methods/devenv-selectstr-method-code-text.md)|X|
|[STRCHECKSUM Method (Code, Text)](../methods/devenv-strchecksum-method-code-text.md)|X|
|[STRLEN Method (Code, Text)](../methods/devenv-strlen-method-code-text.md)|X|
|[STRPOS Method (Code, Text)](../methods/devenv-strpos-method-code-text.md)|X|
|[STRSUBSTNO Method (Code, Text)](../methods/devenv-strsubstno-method-code-text.md)|X|
|[UPPERCASE Method (Code, Text)](../methods/devenv-uppercase-method-code-text.md)|X|

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
[TextBuilder](../api/textbuilder-class.md)